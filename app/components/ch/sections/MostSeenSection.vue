<template>
  <section class="section section--default">
    <div class="container">
      <h2 class="section__title">Meist gesehen</h2>
      <h3 class="section__subtitle">Top Karten</h3>
      <div class="grid grid--responsive-cols-3 gap--responsive">
        <Card type="default">
          <template v-slot:image>
            <img src="https://placekitten.com/g/775/350" alt="cat">
          </template>
          <template v-slot:body>
            <h3 class="card__title">Wandern</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed Lorem ipsum dolor sit amet,
              consetetur sadipscing elitr, sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerInfo>
            Dienstleistungen & Produkte
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowRight"
              label="Weiterlesen"
            />
          </template>
        </Card>
        <Card type="default">
          <template v-slot:image>
            <img src="https://placekitten.com/g/775/350" alt="cat">
          </template>
          <template v-slot:body>
            <h3 class="card__title">Historische Karten</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerInfo>
            Dienstleistungen & Produkte
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowRight"
              label="Weiterlesen"
            />
          </template>
        </Card>
        <Card type="default">
          <template v-slot:image>
            <img src="https://placekitten.com/g/775/350" alt="cat">
          </template>
          <template v-slot:body>
            <h3 class="card__title">PLZ und Ortschaften</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed  Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerInfo>
            Dienstleistungen & Produkte
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowRight"
              label="Weiterlesen"
            />
          </template>
        </Card>
      </div>

      <h3 class="section__subtitle">Top Themen</h3>
      <div class="grid grid--responsive-cols-3 gap--responsive">
        <Card type="default">
          <template v-slot:body>
            <h3 class="card__title">Are</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowUpRight"
              label="Weiterlesen"
              rel="external"
            />
          </template>
        </Card>
        <Card type="default">
          <template v-slot:body>
            <h3 class="card__title">Energie</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowUpRight"
              label="Weiterlesen"
              rel="external"
            />
          </template>
        </Card>
        <Card type="default">
          <template v-slot:body>
            <h3 class="card__title">Luftfahrt</h3>
            <p>
              Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed  Lorem ipsum dolor sit amet, consetetur sadipscing elitr,
              sed Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
            </p>
          </template>
          <template v-slot:footerAction>
            <Btn
              to="#"
              variant="outline"
              icon-pos="only"
              icon="ArrowUpRight"
              label="Weiterlesen"
              rel="external"
            />
          </template>
        </Card>
      </div>

    </div>
  </section>
</template>

<script>
import Card from '~/components/ch/components/Card.vue';
import Btn from "~/components/ch/components/Btn";
import SvgIcon from '../components/SvgIcon.vue';

export default {
  name: 'MostSeenSection',
  components: {
    Card,
    Btn,
    SvgIcon,
  },
};
</script>
