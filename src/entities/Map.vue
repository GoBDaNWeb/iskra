<script setup>
let center = [55.84742656888428, 37.478171499999995];

function init() {
  let map = new ymaps.Map("map", {
    center: center,
    zoom: 17,
  });

  let placemark = new ymaps.Placemark(
    center,
    {},
    {
      iconLayout: "default#image",
      iconImageHref: "@/shared/assets/images/pin.png",
      iconImageSize: [40, 40],
      iconImageOffset: [-19, -44],
    }
  );

  map.controls.remove("geolocationControl"); // удаляем геолокацию
  map.controls.remove("searchControl"); // удаляем поиск
  map.controls.remove("trafficControl"); // удаляем контроль трафика
  map.controls.remove("typeSelector"); // удаляем тип
  map.controls.remove("fullscreenControl"); // удаляем кнопку перехода в полноэкранный режим
  map.controls.remove("zoomControl"); // удаляем контрол зуммирования
  map.controls.remove("rulerControl"); // удаляем контрол правил
  map.behaviors.disable(["scrollZoom"]); // отключаем скролл карты (опционально)

  map.geoObjects.add(placemark);
}

ymaps.ready(init);
</script>

<template>
  <div id="map" class="map"></div>
</template>

<style lang="scss" scoped>
@import "@/shared/styles/vars";

.map {
  width: 100%;
  height: 100%;
  border-radius: 12px;
  border: 1px solid var(--gray-color);
  overflow: hidden;
  @media (max-width: $tab) {
    border-radius: 0px;
  }
}
</style>
