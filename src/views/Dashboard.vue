<template>
  <v-flex shrink>
    <!-- <v-tooltip right>
      <template v-slot:activator="{ on }">
        <v-btn :href="source" icon large target="_blank" v-on="on">
          <v-icon large>code</v-icon>
        </v-btn>
      </template>
      <span>Source</span>
    </v-tooltip>
    <v-tooltip right>
      <template v-slot:activator="{ on }">
        <v-btn icon large href="https://codepen.io/johnjleider/pen/qxQWda" target="_blank" v-on="on">
          <v-icon large>mdi-codepen</v-icon>
        </v-btn>
      </template>
      <span>Codepen</span>
    </v-tooltip> -->
    <v-layout wrap align-center>
      <v-flex>
        <v-text-field
          v-model="message2"
          solo
          label="Solo"
          clearable
          class="custom-input" 
        ></v-text-field>
      </v-flex>
      <v-flex>
        <v-select
          :items="items"
          label="Solo field"
          class="custom-input custom-select"
          :menu-props="{'offset-y':true}"
          solo
        ></v-select>
      </v-flex>
      <v-flex>
        <v-select
          :items="items"
          label="Solo field"
          class="custom-input custom-select"
          solo
        ></v-select>
      </v-flex>
    </v-layout>
  </v-flex>
</template>

<script>
export default {
  name: 'Dashboard',
  data: () => ({
    items: ['Foo', 'Bar', 'Fizz', 'Buzz']
  })
}
</script>
<style>

/* custom-input */
.custom-input{
  font-size: 13px;
}
.custom-input.v-input input{
  padding: 0;
  margin-top: 0px;
  max-height: 26px;
}
.custom-input .v-input__append-inner{
  margin-top: 0px !important;
  /* background: red; */
}
.custom-input .v-label {
  font-size: 13px;
  color: #ccc;
}
.custom-input .v-input__slot{
  box-shadow: none !important;
  padding: 0 5px !important;
  margin-bottom: 0px;
  min-height: 24px !important;
  border: 1px solid #ccc !important;
  border-radius: 2px !important;
}
.custom-input .v-text-field__details {
  display: none;
}
.custom-input .v-input__control,
.custom-input .v-text-field.v-text-field--solo .v-input__control {
  min-height: 24px !important;
}
.custom-input .v-input__icon{
  height: 24px !important;
}
/* custom-select */
.custom-select .v-select__selection--comma{
  position: absolute;
  left: 0;
  margin: 0 !important;
}
.custom-select .v-select__selections{
  /* background: pink; */
}
</style>

