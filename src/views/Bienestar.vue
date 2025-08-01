<template>
  <div class="container">
    <div class="q-pa-md q-gutter-sm">
      <q-dialog v-model="fixed">
        <q-card>
          <q-card-section>
            <div class="text-h3" id="title">{{ dialogTitle }}</div>
          </q-card-section>

          <q-separator />

          <q-card-section class="card-section">
            <div v-for="(img, index) in dialogImages" :key="index" class="img-container">
              <img :src="img" class="img" />
            </div>
            <p>{{ dialogText }}</p>
          </q-card-section>
        </q-card>
      </q-dialog>

      <div class="row justify-center q-gutter-sm">
        <q-intersection v-for="(item, index) in items" :key="index" class="example-item">
          <q-card flat bordered class="q-ma-sm">
            <img
              :src="item.imageUrl"
              class="card-image"
              @click="showDialog(item)"
              style="cursor: pointer"
            />
            <q-card-section>
              <div class="text-h5">{{ item.title }}</div>
            </q-card-section>
          </q-card>
        </q-intersection>
      </div>
    </div>
    <Footer class="footer" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import Footer from "@/components/Footer.vue";

const fixed = ref(false);
const dialogTitle = ref("");
const dialogText = ref("");
const dialogImages = ref("");

function showDialog(item) {
  dialogTitle.value = item.title;
  dialogText.value = item.dialogText;
  dialogImages.value = item.dialogImages;
  fixed.value = true;
}
//Aquí se definen los datos para cada tarjeta, incluyendo título e imagen
const items = ref([
  {
    title: "Día de la Mujer",
    imageUrl:
      "https://i.pinimg.com/originals/d0/28/49/d02849269d00094b1109921a20d4ed87.jpg", // URL DE LA IMAGEN DE GOOGLE
    dialogImages: [
      "/fotosBienestar/mujer.png",
      "/fotosBienestar/mujerregalo.jpg"
    ]
  },
  {
    title: "Día de la Secretaria",
    imageUrl:
      "https://www.elinformador.com.co/images/stories/sociales/2019/04-abril/26entrete.jpg",
    dialogImages: [
      "/fotosBienestar/secretaria.png",
      "/fotosBienestar/fotosecretaria.jpg"
    ]
  },
  {
    title: "Día de la madre",
    imageUrl:
      "https://www.shutterstock.com/image-vector/feliz-dia-de-la-madre-600nw-2290617869.jpg",
    dialogImages: ["/fotosBienestar/madre.png"]
  },
  {
    title: "Reconocimientos",
    imageUrl:
      "https://media.istockphoto.com/id/1264090986/es/vector/equipo-de-empleados-felices-ganando-el-premio.jpg?s=612x612&w=0&k=20&c=XPiqBHIvvE-6aqVd2bIYv9m7-1X5Kf1vvtQ5ZLkF_sI=",
    dialogImages: [
      "/fotosBienestar/detalles.jpg",
      "/fotosBienestar/reconocimientos.jpg",
      "/fotosBienestar/detalles.png"
    ]
  },
  {
    title: "Integraciones",
    imageUrl:
      "https://img.freepik.com/vetores-gratis/gerenciamento-de-tempo-metodo-de-calendario-planejamento-de-compromissos-organizador-de-negocios-pessoas-desenhando-a-marca-em-personagens-de-desenhos-animados-de-cronograma-de-trabalho-trabalho-em-equipe-de-colegas_335657-2096.jpg",
    dialogText: "",
    dialogImages: [
      "/fotosBienestar/integracion.jpeg",
      "/fotosBienestar/integracion2.jpeg",
      "/fotosBienestar/integracion3.png",
      "/fotosBienestar/integracion4.jpeg",
      "/fotosBienestar/integracion5.jpeg",
      "/fotosBienestar/integracion6.jpeg",
      "/fotosBienestar/integracion7.jpeg",
      "/fotosBienestar/integracion8.jpeg"
    ]
  },
  {
    title: "Capacitaciones",
    imageUrl:
      "https://atrevete.academy/blog/wp-content/uploads/2019/08/business-training-concept_171919-1.jpg",
    dialogImages: [
      "/fotosBienestar/capacitacion.jpeg",
      "/fotosBienestar/capacitacion2.jpeg",
      "/fotosBienestar/capacitacion3.jpeg",
      "/fotosBienestar/capacitacion4.jpeg",
      "/fotosBienestar/capacitacion6.jpeg",
      "/fotosBienestar/capacitacion7.jpeg",
      "/fotosBienestar/capacitacion8.jpeg"
    ]
  },
  {
    title: "Cumpleaños",
    imageUrl:
      "https://latinopinionbaltimore.com/wp-content/uploads/2023/12/3642037.jpg",
    dialogImages: [
      "/fotosBienestar/cumpleaños.jpeg",
      "/fotosBienestar/cumpleaños2.jpeg",
      "/fotosBienestar/cumpleaños3.jpeg",
      "/fotosBienestar/cumpleaños4.jpeg",
      "/fotosBienestar/cumpleaños5.jpeg",
      "/fotosBienestar/cumpleaños6.jpeg",
      "/fotosBienestar/cumpleaños7.jpeg"
    ]
  },
  {
    title: "Pausas Activas",
    imageUrl:
      "https://www.anticipacionycontrol.com/wp-content/uploads/2024/01/Como-hacer-pausas-activas.jpg",
    dialogImages: [
      "/fotosBienestar/pausas.jpeg",
      "/fotosBienestar/pausas2.jpeg",
      "/fotosBienestar/pausas3.jpeg",
      "/fotosBienestar/pausas4.jpeg",
      "/fotosBienestar/pausas5.jpeg",
      "/fotosBienestar/pausas6.jpeg",
      "/fotosBienestar/pausas7.jpeg",
      "/fotosBienestar/pausas8.jpeg",
      "/fotosBienestar/pausas9.jpeg"
    ]
  },
  {
    title: "Personal",
    imageUrl:
      "https://media.istockphoto.com/id/1213439458/es/vector/concepto-de-vacante-laboral-y-recursos-humanos.jpg?s=612x612&w=0&k=20&c=w0xiP-IupfNsONwdGpo4wed3ZdcQuHdfjOPyikHunrM=",
    dialogImages: [
      "/fotosBienestar/personal.png",
      "/fotosBienestar/personal2.jpeg",
      "/fotosBienestar/personal3.jpeg",
      "/fotosBienestar/personal4.jpeg",
      "/fotosBienestar/personal5.jpeg"
    ]
  }
]);
</script>

<style scoped>
.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 50px;
}
p {
  font-size: 20px;
  text-align: justify;
}
.card-section {
  width: 500px;
  height: 700px;
}
.footer {
  margin-top: 20%;
}
.img {
  width: 100%;
  margin-bottom: 20px;
}
.example-item {
  height: 290px;
  width: 290px;
}
.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
@media (max-width: 630px) {
  .card-section {
    width: 400px;
    height: 600px;
  }
  #title {
    font-size: 45px;
  }
}
@media (max-width: 450px) {
  .card-section {
    width: 350px;
    height: 600px;
  }
  #title {
    font-size: 40px;
  }
}
@media (max-width: 400px) {
  .card-section {
    width: 320px;
    height: 550px;
  }
  #title {
    font-size: 35px;
  }
  .footer {
    margin-top: 50px;
  }
  p {
    font-size: 15px;
  }
}
@media (max-width: 350px) {
  .card-section {
    width: 290px;
  }
  #title {
    font-size: 30px;
  }
}
</style>
