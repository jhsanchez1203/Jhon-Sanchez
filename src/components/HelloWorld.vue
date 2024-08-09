<template>
  <div class="hello">
    <!--begin::Toolbar-->
    <div class="toolbar" id="kt_toolbar">
      <!--begin::Container-->
      <div id="kt_toolbar_container" class="container-fluid d-flex flex-stack">
        <!--begin::Page title-->
        <div data-kt-swapper="true" data-kt-swapper-mode="prepend"
          data-kt-swapper-parent="{default: '#kt_content_container', 'lg': '#kt_toolbar_container'}"
          class="page-title d-flex align-items-center flex-wrap me-3 mb-5 mb-lg-0">
          <!--begin::Title-->
          <h1 class="d-flex align-items-center text-dark fw-bolder fs-3 my-1">Reto técnico Frontend Developer Vue JS
          </h1>
          <!--end::Title-->
          <!--begin::Separator-->

          <!--end::Separator-->

        </div>
        <!--end::Page title-->

      </div>
      <!--end::Container-->
    </div>
    <!--end::Toolbar-->
    <br>
    <!--begin::Post-->
    <div class="post d-flex flex-column-fluid" id="kt_post">
      <!--begin::Container-->
      <div id="kt_content_container" class="container-xxl">

        <!--begin::Tables Widget 13-->
        <div class="card mb-5 mb-xl-8">
          <!--begin::Header-->
          <div class="card-header border-0 pt-5">
            <h3 class="card-title align-items-start flex-column">
              <span class="card-label fw-bolder fs-3 mb-1">Listado de Películas</span>

            </h3>
            <hr style="width: 100%;color:rgba(0, 0, 0, 4) !important;" >
            <div class="row" style="width: 100%;margin-top: 20px;">
              <div class="col">
                <span>Título</span> <br>
                <div class="position-relative">
                  <!--begin::Svg Icon | path: icons/duotune/general/gen021.svg-->
                  <span class="svg-icon svg-icon-3 svg-icon-gray-500 position-absolute top-50 translate-middle ms-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
                      <rect opacity="0.5" x="17.0365" y="15.1223" width="8.15546" height="2" rx="1"
                        transform="rotate(45 17.0365 15.1223)" fill="black" />
                      <path
                        d="M11 19C6.55556 19 3 15.4444 3 11C3 6.55556 6.55556 3 11 3C15.4444 3 19 6.55556 19 11C19 15.4444 15.4444 19 11 19ZM11 5C7.53333 5 5 7.53333 5 11C5 14.4667 7.53333 17 11 17C14.4667 17 17 14.4667 17 11C17 7.53333 14.4667 5 11 5Z"
                        fill="black" />
                    </svg>
                  </span>
                  <!--end::Svg Icon-->
                  <input type="text" class="form-control form-control-solid ps-10" v-model="filtroTitulo" value=""
                    placeholder="Título" @input="filtrarPeliculas" />
                </div>
              </div>
              <div class="col">
                <span>Descripción</span> <br>
                <div class="position-relative">
                  <!--begin::Svg Icon | path: icons/duotune/general/gen021.svg-->
                  <span class="svg-icon svg-icon-3 svg-icon-gray-500 position-absolute top-50 translate-middle ms-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
                      <rect opacity="0.5" x="17.0365" y="15.1223" width="8.15546" height="2" rx="1"
                        transform="rotate(45 17.0365 15.1223)" fill="black" />
                      <path
                        d="M11 19C6.55556 19 3 15.4444 3 11C3 6.55556 6.55556 3 11 3C15.4444 3 19 6.55556 19 11C19 15.4444 15.4444 19 11 19ZM11 5C7.53333 5 5 7.53333 5 11C5 14.4667 7.53333 17 11 17C14.4667 17 17 14.4667 17 11C17 7.53333 14.4667 5 11 5Z"
                        fill="black" />
                    </svg>
                  </span>
                  <!--end::Svg Icon-->
                  <input type="text" class="form-control form-control-solid ps-10" v-model="filtroDescripcion" value=""
                    placeholder="Descripción" @input="filtrarPeliculas" />
                </div>
              </div>
              <div class="col">
                <span>Género</span>
                
                <select multiple class="form-control" v-model="filtroGeneros" @change="filtrarPeliculas" >
                  
                  <option v-for="genero in generos" :key="genero" :value="genero">
                    {{ genero }}
                  </option>
                </select>
              </div>
            </div>
            <hr style="width: 100%;color:rgba(0, 0, 0, 4) !important;" >
          </div>
          <!--end::Header-->
          
          <!--begin::Body-->
          <div class="card-body py-3">
            <!--begin::Table container-->
            <div class="table-responsive">
              <!--begin::Table-->
              <table class="table table-row-bordered table-row-gray-100 align-middle gs-0 gy-3">
                <!--begin::Table head-->
                <thead>
                  <tr class="fw-bolder text-muted">

                    <th class="min-w-150px">Id</th>
                    <th class="min-w-140px">Título</th>
                    <th class="min-w-120px">Descripción</th>
                    <th class="min-w-120px">Género</th>
                  </tr>
                </thead>
                <!--end::Table head-->
                <!--begin::Table body-->
                <tbody>
                  <tr v-for="pelicula in peliculasFiltradas" :key="pelicula.id">

                    <td>
                      <b>{{ pelicula.id }}</b>
                    </td>
                    <td>
                      {{ pelicula.titulo }}

                    </td>
                    <td>
                      {{ pelicula.descripcion }}

                    </td>
                    <td>
                      {{ pelicula.genero }}

                    </td>

                  </tr>

                </tbody>
                <!--end::Table body-->
              </table>
              <!--end::Table-->
            </div>
            <!--end::Table container-->
          </div>
          <!--begin::Body-->
        </div>
        <!--end::Tables Widget 13-->
      </div>
      <!--end::Container-->
    </div>
    <!--end::Post-->

  </div>

</template>

<script>
import { defineComponent } from 'vue';
import axios from 'axios';
export default defineComponent({
  name: 'HelloWorld',
  data() {
    return {
      peliculas: [],
      generos: [],
      generosSeleccionados: [],
      filtroTitulo: "",
      filtroDescripcion: "",
      filtroGeneros: [],
      peliculasFiltradas: []
    };
  },
  methods: {
    async fetchData() {
      try {
        //Lectura de archivo json con axios
        const response = await axios.get('/assets/data/peliculas.json');
        //Llenado de datos traidos del archivo en mis variables creadas
        this.peliculas = response.data.peliculas;
        this.generos = response.data.generos;
        this.peliculasFiltradas = this.peliculas;
      } catch (error) {
        console.error('Error al cargar el archivo JSON:', error);
      }
    },
    //Función para filtrar el listado de películas por título, descripción y género de manera mútiple
    filtrarPeliculas() {
      
      const titulo = this.filtroTitulo.toLowerCase();
      const descripcion = this.filtroDescripcion.toLowerCase();
      const generosSeleccionados = this.filtroGeneros;

      this.peliculasFiltradas = this.peliculas.filter(pelicula => {
        const coincideTitulo = pelicula.titulo.toLowerCase().includes(titulo);
        const coincideDescripcion = pelicula.descripcion.toLowerCase().includes(descripcion);
        const coincideGenero = 
          generosSeleccionados.length === 0 || 
          generosSeleccionados.includes(pelicula.genero);
        return coincideTitulo && coincideDescripcion && coincideGenero;
      });
    }
  },
  created() {
    this.fetchData();
    
  }
});

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
select {
  width: 100%;
  padding: 8px;
  margin-bottom: 20px;
}
</style>
