<template>
  <Page class="page">
    <ActionBar class="action-bar" title="Hello world">
    </ActionBar>

    <RadSideDrawer ref="drawer">
      <StackLayout ~drawerContent backgroundColor="#eee">
        <Label text="Drawer Content"/>
      </StackLayout>
      <StackLayout ~mainContent class="hello-world">
        <Button class="btn btn-primary" @tap="$refs.drawer.nativeView.toggleDrawerState()" text="Toggle Drawer"/>

        <Label class="body" textWrap=true text="This is a hello world component, tap the button if you dare"/>
        <Button class="btn btn-primary" @tap="surprise = !surprise" text="Tap me!"/>
        <Image v-if="surprise" src="~/images/NativeScript-Vue.png"/>
      </StackLayout>
    </RadSideDrawer>
  </Page>
</template>

<script>
  export default {
    data () {
      return {
        surprise: false,
      };
    },
  };
</script>

<style scoped>
  .hello-world {
    margin: 20;
  }

  Label {
    color: red;
  }
</style>
