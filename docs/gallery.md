<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  if (typeof document === 'undefined') return

  const overlay = document.querySelector('.lightbox-backdrop')
  const overlayImg = overlay?.querySelector('img')
  const closeBtn = overlay?.querySelector('.lightbox-close')

  if (!overlay || !overlayImg || !closeBtn) return

  // Quand on clique sur une image de la galerie -> on ouvre le lightbox
  document.querySelectorAll('.gallery-item img').forEach((img) => {
    img.addEventListener('click', () => {
      overlayImg.src = img.src
      overlayImg.alt = img.alt || ''
      overlay.classList.add('is-open')
    })
  })

  // Fermer le lightbox en cliquant sur le fond ou sur la croix
  overlay.addEventListener('click', (event) => {
    if (event.target === overlay) {
      overlay.classList.remove('is-open')
    }
  })

  closeBtn.addEventListener('click', () => {
    overlay.classList.remove('is-open')
  })

  // Échapper pour fermer
  document.addEventListener('keydown', (event) => {
    if (event.key === 'Escape') {
      overlay.classList.remove('is-open')
    }
  })
})
</script>


# Equestrian Gallery

A visual journey through the discipline, calm, and beauty of the equestrian lifestyle —  
from training routines to peaceful trail rides and quiet moments at the stable.

---

## 🏇 Training Moments

<div class="gallery-grid">

  <figure class="gallery-item">
    <img src="/images/training1.jpg" alt="Training photo 1">
    <figcaption>Improving balance and contact from the saddle.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training2.jpg" alt="Training photo 2">
    <figcaption>Warm-up session focusing on rhythm and suppleness.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training3.jpg" alt="Training photo 3">
    <figcaption>Indoor arena ride during flatwork practice.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training4.jpg" alt="Training photo 4">
    <figcaption>Strengthening leg position and stability.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training5.jpg" alt="Training photo 5">
    <figcaption>Relaxed schooling ride with soft contact.</figcaption>
  </figure>

</div>

---

## 🌲 Trail Rides

<div class="gallery-grid">

  <figure class="gallery-item">
    <img src="/images/training-1.jpg" alt="Trail ride photo 1">
    <figcaption>Golden outdoor lighting during a peaceful ride.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training-2.jpg" alt="Trail ride photo 2">
    <figcaption>A long quiet path — perfect for a relaxed hack.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training-3.jpg" alt="Trail ride photo 3">
    <figcaption>Country ride and a rewarding pat on the neck.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training-4.jpg" alt="Trail ride photo 4">
    <figcaption>Winter trail with fresh snow and open air.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/training-5.jpg" alt="Trail ride photo 5">
    <figcaption>Summer trail ride in a peaceful forest setting.</figcaption>
  </figure>

</div>

---

## 🐴 Behind the Scenes

<div class="gallery-grid">

  <figure class="gallery-item">
    <img src="/images/bts-stall-rest.jpg" alt="Horse resting in stall">
    <figcaption>A calm moment at the stall after training.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/bts-blanket-hay.jpg" alt="Horse eating hay with blanket">
    <figcaption>Evening routine: hay, comfort, and quiet.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/bts-tack-room-wood.jpg" alt="Wooden tack room">
    <figcaption>The warm wooden tack room ready for the next ride.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/bts-tack-room-white.jpg" alt="White tack room">
    <figcaption>An organized tack room with bridles and saddle pads.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/bts-groom-bay.jpg" alt="Horse in grooming bay">
    <figcaption>Moments of connection in the grooming bay.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="/images/bts-two-horses.jpg" alt="Two horses greeting">
    <figcaption>Stable friends greeting each other softly.</figcaption>
  </figure>

</div>

<div class="lightbox-backdrop">
  <button class="lightbox-close" aria-label="Close image">×</button>
  <img src="" alt="Expanded gallery image" />
</div>
