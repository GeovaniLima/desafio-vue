<template>
  <div> 

    <v-container>
      <h3>Editor de Modelo</h3>

      <br>

      <v-row

        justify="space-between"
      >
        <v-col
          cols="12"
          md="6"
        >
          <v-form ref="form">
            <v-select
              :items="items"
              label="Dual Carriageway Rail"
              outlined
            ></v-select>

            <div class="group_radios">
              <div class="vista_movimento">
                <p> Vista de Movimento</p>
                <v-radio-group
                  v-model="radios"
                  mandatory
                >
                  <v-radio
                    label="Esquerda"
                    value="esquerda"
                    color="#00335F"
                  ></v-radio>
                  <v-radio
                    label="Direita"
                    value="direita"
                    color="#00335F"
                  ></v-radio>
                  <v-radio
                    label="Ambos"
                    value="ambos"
                    color="#00335F"
                  ></v-radio>
                </v-radio-group>
              </div>

              <div class="ver">
                <p> Ver </p>
                <v-radio-group
                  v-model="radios"
                  mandatory
                >
                  <v-radio
                    label="Cortar"
                    value="cortar"
                    color="#00335F"
                  ></v-radio>
                  <v-radio
                    label="Preencher"
                    value="preencher"
                    color="#00335F"
                  ></v-radio>
                </v-radio-group>

                <v-select
                  :items="indice"
                  label="Índice V:H"
                  outlined
                ></v-select>
              </div>
            </div>
          </v-form>
        </v-col>

        <v-col
          cols="12"
          md="6"
        >
          <h2>Trilho</h2>

          <p>Balastro</p>
          <v-text-field
            v-model="largura"
            label="Largura"
            suffix="m2"
            color="#00335F"
            outlined
          ></v-text-field>
          <v-text-field
            v-model="altura"
            label="Altura"
            suffix="m2"
            color="#00335F"
            outlined
          ></v-text-field>
          <v-text-field
            v-model="declive"
            label="Declive"
            suffix="(%)"
            color="#00335F"
            outlined
          ></v-text-field>
          <v-checkbox
            v-model="superelevacao"
            label="Super Elevação"
            color="#00335F"
          ></v-checkbox>

          <p>Rastrear</p>
          <v-text-field
            v-model="medidor"
            label="Medidor 1/2"
            suffix="mm"
            color="#00335F"
            outlined
          ></v-text-field>
        </v-col>
      </v-row>

      <div class="contaneir-img">

        <v-checkbox
          v-model="zoomajuste"
          label="Zoom Ajuste"
          color="#00335F"
        ></v-checkbox>
        <v-img
          height="300"
          src="https://www.tecnolegis.com/media/imagens/provas-fev-12/2012/metro/metrosp-metroviarios-agrimensura-q-35e36.png"
        ></v-img>  
      </div> 

      <div class="container-buttons">
        <v-btn class="btn-ok">
          Ok
        </v-btn>
        <v-btn color="error">
          Cancelar
        </v-btn> 
      </div>
    </v-container>

  </div>
</template>

<script>

export default {
  name: 'HomeView',
  components: {
  },
  data: () => ({
    items: [
      'Median_1', 
      'Shoulder_1', 
      'Rail_1', 
      'Shoulder_2',
      'Subgrade_1',
      'Subgrade_2',
      'Ditch_1'
    ],
    indice: [
      '1:1'
    ],
  }),
}
</script>

<style>
  .group_radios {
    flex: 1;
    display: flex;
    justify-content: space-between;
  }

  .contaneir-img {
    margin-bottom: 50px;
  }

  .container-buttons {
    display: flex;
    justify-content: flex-end;
  }

  .container-buttons .btn-ok {
    margin-right: 5px;

    background-color: #00335F !important;
    color: #FFF;
  }
</style>
