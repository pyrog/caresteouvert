<template>
  <v-dialog
    v-model="dialog"
    :eager="true"
    :width="600"
  >
    <template v-slot:activator="{ on }">
      <v-list-item v-on="on">
        <v-list-item-icon class="mr-0">
          <v-icon small>osm-info</v-icon>
        </v-list-item-icon>
        <v-list-item-content class="ml-2">
          <v-list-item-title class="body-1">{{ $t('learnmore.title') }}</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </template>

    <v-card>
      <v-card-title>
        {{ $t('learnmore.title') }}
        <v-spacer></v-spacer>
        <v-btn
          icon
          @click="dialog = false"
        >
          <v-icon>osm-close</v-icon>
        </v-btn>
      </v-card-title>
      <v-card-text>
        <span class="text-pre">{{ $t('learnmore.description', { brand }) }}</span>
        <v-row>
          <v-col
            cols="12"
            md="6"
          >
            <h2 class="mb-3">{{ $t('learnmore.contribute') }}</h2>
            <ul>
              <li>
                <a :href="links.shopMissing">
                  {{ $t('learnmore.missing_shop') }}
                </a>
              </li>
              <li>
                <a :href="links.townhalls">
                  {{ $t('learnmore.townhalls', { brand }) }}
                </a>
              </li>
            </ul>
          </v-col>
          <v-col
            cols="12"
            md="6"
          >
            <h2 class="mb-3">{{ $t('learnmore.about') }}</h2>
            <ul>
              <li>
                <a :href="links.blog">
                  {{ $t('learnmore.blog') }}
                </a>
              </li>
              <li>
                <a :href="links.about">
                  {{ $t('learnmore.about') }}
                </a>
              </li>
              <li>
                <a :href="links.press">
                  {{ $t('learnmore.press') }}
                </a>
              </li>
              <li>
                <a :href="links.disclaimer">
                  {{ $t('learnmore.disclaimer') }}
                </a>
              </li>
            </ul>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
import i18nMixin from './mixins/i18n';

export default {
  mixins: [i18nMixin],

  data() {
    return {
      dialog: false
    };
  }
};
</script>
