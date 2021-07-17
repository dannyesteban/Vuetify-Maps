<template>
  <v-menu :rounded="'b-xl'">
    <template v-slot:activator="{ on }">
      <v-badge
        :content="items.length"
        :value="items.length"
        color="blue"
        overlap
      >
        <v-icon v-on="on" medium>notifications_active</v-icon>
      </v-badge>
    </template>

    <v-card max-width="500" class="mx-auto">
      <v-toolbar color="blue" dark>
        <v-toolbar-title>{{ items.length }} New Notifications</v-toolbar-title>
        <v-spacer></v-spacer>
      </v-toolbar>

      <v-list two-line class="overflow-y-auto" max-height="400">
        <v-list-item-group active-class="blue--text">
          <template v-for="(item, index) in items">
            <v-list-item :key="item.title" @click="fnGoToDriver(item)">
              <template>
                <v-list-item-content>
                  <v-list-item-title v-text="item.title"></v-list-item-title>
                  <v-list-item-subtitle
                    class="text--primary"
                    v-text="item.headline"
                  ></v-list-item-subtitle>
                  <v-list-item-subtitle
                    v-text="item.subtitle"
                  ></v-list-item-subtitle>
                </v-list-item-content>

                <v-list-item-action>
                  <v-list-item-action-text
                    v-text="item.action"
                  ></v-list-item-action-text>
                </v-list-item-action>
              </template>
            </v-list-item>
            <v-divider :key="index"></v-divider>
          </template>
        </v-list-item-group>
      </v-list>
    </v-card>
  </v-menu>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        action: "15 min",
        headline: "Brunch this weekend?",
        title: "Ali Connors",
        subtitle:
          "I'll be in your neighborhood doing errands this weekend. Do you want to hang out? Wish I could come, but I'm out of town this weekend.",
      },
      {
        action: "2 hr",
        headline: "Summer BBQ",
        title: "me, Scrott, Jennifer",
        subtitle: "Wish I could come, but I'm out of town this weekend.",
      },
      {
        action: "6 hr",
        headline: "Oui oui",
        title: "Sandra Adams",
        subtitle: "Do you have Paris recommendations? Have you ever been?",
      },
      {
        action: "12 hr",
        headline: "Birthday gift",
        title: "Trevor Hansen",
        subtitle:
          "Have any ideas about what we should get Heidi for her birthday?",
      },
      {
        action: "18hr",
        headline: "Recipe to try",
        title: "Britta Holt",
        subtitle:
          "We should eat this: Grate, Squash, Corn, and tomatillo Tacos.",
      },
    ],
  }),
  methods: {
    fnGoToDriver(item) {
      this.items.pop();
      //this.$router.push({ name: "driverId", params: { id: item._id } });
    },

    fnGetNotifications() {
      this.items = [
        {
          action: "15 min",
          headline: "Brunch this weekend?",
          title: "Ali Connors",
          subtitle:
            "I'll be in your neighborhood doing errands this weekend. Do you want to hang out? Wish I could come, but I'm out of town this weekend.",
        },
        {
          action: "2 hr",
          headline: "Summer BBQ",
          title: "me, Scrott, Jennifer",
          subtitle: "Wish I could come, but I'm out of town this weekend.",
        },
        {
          action: "6 hr",
          headline: "Oui oui",
          title: "Sandra Adams",
          subtitle: "Do you have Paris recommendations? Have you ever been?",
        },
        {
          action: "12 hr",
          headline: "Birthday gift",
          title: "Trevor Hansen",
          subtitle:
            "Have any ideas about what we should get Heidi for her birthday?",
        },
        {
          action: "18hr",
          headline: "Recipe to try",
          title: "Britta Holt",
          subtitle:
            "We should eat this: Grate, Squash, Corn, and tomatillo Tacos.",
        },
        {
          action: "55hr",
          headline: "Job",
          title: "Danny Acosta",
          subtitle: "I'm a web developer",
        },
      ];
    },
  },
  mounted() {
    this.fnGetNotifications();
  },
};
</script>