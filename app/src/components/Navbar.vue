<template>
   <nav>
    <v-app-bar color="orange" dark app>
        <v-app-bar-nav-icon @click.stop="drawer = !drawer">

        </v-app-bar-nav-icon>
        <v-toolbar-title class="text-uppercase">
            <span class="font-weight-light">PM</span>
            <span>Project managment App</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-menu offset-y>
            <template v-slot:activator="{ on }">
                    <v-btn text v-on="on">
                        <v-icon left>expand_more</v-icon>
                        <span>Menu</span>
                    </v-btn>
            </template>
            <v-list flat>
                <v-list-item v-for="link in links" :key="link.text" router :to="link.route" active-class="border">
                    <v-list-item-title>{{link.text}}</v-list-item-title>
                </v-list-item>
            </v-list>
        </v-menu>
        <v-btn text>
            <span>Exit</span>
            <v-icon right>exit_to_app</v-icon>
        </v-btn>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" dark app class="orange darken-4">
        <v-layout column align-center>
            <v-flex class="mt-5">
                <v-avatar size="100">
                    <v-img src="../assets/user.png"></v-img>
                    <p class="white--text subheading mt-1 text-center">Username</p>
                </v-avatar>
            </v-flex>
        </v-layout>
        <v-list flat>
            <v-list-item v-for="link in links" :key="link.text" router :to="link.route" active-class="border">
                <v-list-item-action>
                    <v-icon>{{link.text}}</v-icon>
                </v-list-item-action>
                <v-list-item-content>
                    <v-list-item-title>{{link.text}}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
    name: 'Navbar',
    data: () => ({
        drawer : true,
        links: [
            {icon: 'dashboard', text: 'Dashboard', route:'/'},
            {icon: 'folder', text: 'My Projects', route:'/projects'},
            {icon: 'person', text: 'Team', route:'/team'},
        ]
    })
}
</script>

<style>
.border {
    border-left: 4px solid #0ba518;
}
</style>