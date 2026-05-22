<template>
  <div class="testimonials-container">
    <div class="testim-gradient testim-gradient-left"></div>
    <div class="testim-gradient testim-gradient-right"></div>

    <swiper-container
      :slides-per-view="1.2"
      :space-between="20"
      :loop="true"
      :speed="5000"
      :autoplay="{
        delay: 0,
        disableOnInteraction: false,
      }"
      :free-mode="true"
      :breakpoints="{
        640: { slidesPerView: 2 },
        1024: { slidesPerView: 3.5 },
        1440: { slidesPerView: 4.5 }
      }"
      class="continuous-swiper"
    >
      <swiper-slide v-for="(item, index) in testimonials" :key="index" class="testim-slide">
        <div class="glass-card testim-card group">
          <div>
            <div class="testim-quote-icon">"</div>
            <p class="testim-text">
              {{ item.quote }}
            </p>
          </div>
          
          <div class="testim-author">
            <img :src="item.image" :alt="item.name" class="testim-avatar" />
            <div class="testim-author-info">
              <h4 class="testim-name">{{ item.name }}</h4>
              <p class="testim-company">{{ item.company }}</p>
            </div>
          </div>
        </div>
      </swiper-slide>
    </swiper-container>
  </div>
</template>

<script setup>
import { register } from 'swiper/element/bundle';
register();

const testimonials = [
  {
    name: "Ricardo Silva",
    company: "Silva Imóveis",
    quote: "A DS Desenvolvimento transformou completamente nossa presença digital. Em menos de 3 meses, o volume de leads qualificados triplicou.",
    image: "https://i.pravatar.cc/150?u=ricardo"
  },
  {
    name: "Marcos Vinícius",
    company: "TechSolutions",
    quote: "Trabalho com tecnologia e sou exigente. O código deles é limpo e a performance no Google é impecável. Recomendo!",
    image: "https://i.pravatar.cc/150?u=marcos"
  },
  {
    name: "Fabiola Mendes",
    company: "Mendes Advocacia",
    quote: "Nossa Landing Page converte 4x mais que o site antigo. A clareza da proposta de valor e a velocidade fazem toda a diferença.",
    image: "https://i.pravatar.cc/150?u=fabio"
  },
  {
    name: "Bruno Guedes",
    company: "Guedes Logística",
    quote: "Eles entendem de negócio, não só de código. A consultoria estratégica inicial poupou meses de erros no nosso marketing.",
    image: "https://i.pravatar.cc/150?u=bruno"
  },
  {
    name: "Rudney Ramos",
    company: "Incoplim",
    quote: "Foi muito positivo para minha loja de produtos de limpeza, aumentou muito o número de clientes! Ajudou muito meu rankeamento no Google",
    image: "https://i.pravatar.cc/150?u=rudney"
  }
];
</script>

<style scoped src="../styles/components/Testimonials.css"></style>
