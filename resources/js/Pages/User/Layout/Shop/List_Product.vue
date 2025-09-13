<script setup>
import { Link } from "@inertiajs/vue3";
import Comment from "../Comment.vue";
import Swal from "sweetalert2";
import { ref, onMounted } from "vue";

// reactive state
const count = ref(1);
const mainImage = ref("");
const currentImage = ref("");
const statusProduct = ref("In Stock");

// product images
const user1 = ref("");
const user2 = ref("");
const user3 = ref("");
const product1 = ref("");
const product2 = ref("");
const product3 = ref("");
const product4 = ref("");
const product5 = ref("");
const product6 = ref("");
const product7 = ref("");
const product8 = ref("");
const product9 = ref("");
const product10 = ref("");
const product11 = ref("");
const product12 = ref("");

// lifecycle
onMounted(() => {
    user1.value = "/assets/img/users/ajiw.png";
    user2.value = "/assets/img/users/aji.jpg";
    user3.value = "/assets/img/users/profil.JPG";

    product1.value = "/assets/products/pohon1.jpg";
    mainImage.value = "/assets/products/pohon1.jpg";
    currentImage.value = "/assets/products/pohon1.jpg";

    product2.value = "/assets/products/pohon2.jpg";
    product3.value = "/assets/products/pohon3.jpg";
    product4.value = "/assets/products/pohon4.jpg";
    product5.value = "/assets/products/pohon5.jpg";
    product6.value = "/assets/products/pohon6.jpg";
    product7.value = "/assets/products/product7.jpg";
    product8.value = "/assets/products/product8.jpg";
    product9.value = "/assets/products/product9.jpg";
    product10.value = "/assets/products/product10.jpg";
    product11.value = "/assets/products/product11.jpg";
    product12.value = "/assets/products/product12.jpg";
});

// methods
function increment() {
    if (count.value < 10) {
        count.value++;
    } else {
        Swal.fire({
            icon: "info",
            title: "Perhatian",
            text: "Anda telah mencapai jumlah minimal pembelian",
            timer: 3000,
            iconColor: "#ffe066",
        });
    }
}

function decrement() {
    if (count.value > 1) {
        count.value--;
    } else {
        Swal.fire({
            icon: "info",
            title: "Perhatian",
            text: "Anda telah mencapai jumlah maksimal pembelian",
            timer: 3000,
            iconColor: "#ffe066",
        });
    }
}

function changeMainImage(imageSrc) {
    currentImage.value = imageSrc;
}

function resetMainImage() {
    currentImage.value = mainImage.value;
}

function popupSuccess() {
    Swal.fire({
        title: "Sukses",
        text: "Produk berhasil ditambahkan",
        icon: "success",
        timer: 3000,
        iconColor: "#3CB72B",
    });
}

function popupFavorite() {
    Swal.fire({
        position: "top-end",
        icon: "success",
        title: "Sukses",
        text: "Produk berhasil ditambahkan ke favorite",
        showConfirmButton: false,
        timer: 2000,
        iconColor: "#3CB72B",
    });
}
</script>
