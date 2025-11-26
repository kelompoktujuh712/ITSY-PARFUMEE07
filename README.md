
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flowerss Parfum - Wangi Bikin Menarik!</title>
    <!-- Memuat Tailwind CSS --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Memuat Google Fonts (Pacifico untuk Footer, Inter untuk utama) --><link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        /* Mengatur font utama dan beberapa utilitas global */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #fce7f3; /* Pink sangat muda sebagai latar */
            overflow-x: hidden;
        }

        /* Kelas untuk font Joypops/Bubble Pop simulasi */
        .font-pacifico {
            font-family: 'Pacifico', cursive;
        }

        /* --- Animasi Bunga Berjatuhan (Falling Flowers Animation) --- */
        .flower-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none; /* Agar tidak menghalangi klik */
            overflow: hidden;
            z-index: 0; /* Pastikan di belakang konten */
        }

        .flower {
            position: absolute;
            color: #f9a8d4; /* Pink lembut */
            font-size: 1.5rem;
            opacity: 0.8;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% {
                transform: translateY(-10vh) translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(100vh) translateX(20vw) rotate(360deg);
                opacity: 0;
            }
        }

        /* CSS kustom untuk tombol CTA yang eye-catching */
        .cta-button {
            transition: all 0.3s ease;
            box-shadow: 0 4px 6px -1px rgba(244, 114, 182, 0.5), 0 2px 4px -2px rgba(244, 114, 182, 0.5);
        }
        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 15px -3px rgba(236, 72, 153, 0.7), 0 4px 6px -4px rgba(236, 72, 153, 0.7);
        }

        /* Styling untuk Modal */
        .modal-overlay {
            background-color: rgba(0, 0, 0, 0.6);
            z-index: 999;
        }
        .modal-content {
            transform: scale(0.95);
            animation: popIn 0.3s ease-out forwards;
        }
        @keyframes popIn {
            to { transform: scale(1); opacity: 1; }
        }

    </style>
</head>
<body class="relative">

    <!-- Kontainer Bunga Berjatuhan --><div class="flower-container">
        <!-- Bunga akan di-generate oleh JS, tapi kita tambahkan beberapa secara statis sebagai fallback --><span class="flower" style="left: 10%; animation-duration: 15s; animation-delay: 0s;">🌸</span>
        <span class="flower" style="left: 30%; animation-duration: 12s; animation-delay: 5s;">🌼</span>
        <span class="flower" style="left: 60%; animation-duration: 18s; animation-delay: 10s;">🌺</span>
        <span class="flower" style="left: 80%; animation-duration: 10s; animation-delay: 2s;">🌷</span>
    </div>

    <!-- Navigasi Bar --><header class="sticky top-0 z-50 bg-pink-500 shadow-lg bg-opacity-95 backdrop-blur-sm">
        <nav class="container mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
            <a href="#beranda" class="text-2xl font-bold text-white font-pacifico">flowerss parfum</a>
            <div class="hidden md:flex space-x-8">
                <a href="#beranda" class="text-white hover:text-pink-200 transition duration-300">Beranda</a>
                <a href="#produk" class="text-white hover:text-pink-200 transition duration-300">Produk</a>
                <a href="#tentang" class="text-white hover:text-pink-200 transition duration-300">Tentang Kami</a>
                <a href="#testimoni" class="text-white hover:text-pink-200 transition duration-300">Testimoni</a>
            </div>
            <!-- Tombol Keranjang --><button onclick="openModal('cart-modal')" class="relative p-2 rounded-full bg-pink-600 text-white hover:bg-pink-700 transition duration-300">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
                </svg>
                <span id="cart-count" class="absolute top-0 right-0 inline-flex items-center justify-center px-2 py-1 text-xs font-bold leading-none text-red-100 transform translate-x-1/2 -translate-y-1/2 bg-red-600 rounded-full">0</span>
            </button>
        </nav>
    </header>

    <main class="relative z-10">
        <!-- Bagian Beranda (Hero) --><section id="beranda" class="min-h-[80vh] flex items-center justify-center text-center py-20 bg-pink-100 shadow-inner">
            <div class="max-w-4xl px-4">
                <h1 class="text-5xl sm:text-7xl font-extrabold text-pink-700 mb-4 animate-pulse">
                    Wangi kan badan mu dengan parfum roll
                </h1>
                <p class="text-xl sm:text-2xl text-pink-600 font-semibold mb-8">
                    parfum roll dengan wangi bikin menarik!!
                </p>
                <a href="#produk" class="cta-button inline-block bg-pink-500 text-white text-lg font-bold py-3 px-8 rounded-full hover:bg-pink-600 transition duration-300">
                    Lihat Produk Kami
                </a>
            </div>
        </section>

        <!-- Bagian Produk --><section id="produk" class="container mx-auto px-4 py-16">
            <h2 class="text-4xl font-bold text-center text-pink-700 mb-12">Produk Parfum Roll Kami</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Produk 1: Nagita Roll --><div class="bg-white rounded-xl shadow-2xl overflow-hidden hover:shadow-pink-400 transition duration-500">
                    <img src="https://down-id.img.susercontent.com/file/id-11134207-7r990-lnduo9yi0h9729" alt="Nagita Roll Parfum" onerror="this.onerror=null;this.src='https://placehold.co/400x400/FFD1DC/333?text=Nagita+Roll+Parfum'" class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-bold text-pink-600 mb-2">Nagita Roll</h3>
                        <p class="text-xl font-extrabold text-pink-700 mb-4">Rp 7.000</p>
                        <p class="text-gray-600 mb-6">Aroma klasik yang elegan, memancarkan pesona mewah yang tak lekang oleh waktu. Sempurna untuk penampilan berkelas dan memikat.</p>
                        <button onclick="addToCart({id: 'nagita', name: 'Nagita Roll', price: 7000})" class="cta-button w-full bg-pink-500 text-white font-bold py-3 rounded-full">
                            Pesan Sekarang!
                        </button>
                    </div>
                </div>
                <!-- Produk 2: Sweet Boo Roll -->
                <div class="bg-white rounded-xl shadow-2xl overflow-hidden hover:shadow-pink-400 transition duration-500">
                    <img src="https://down-id.img.susercontent.com/file/id-11134207-7r98s-lnduo9yhw9jv54" alt="Sweet Boo Roll Parfum" onerror="this.onerror=null;this.src='https://placehold.co/400x400/FFA07A/333?text=Sweet+Boo+Roll+Parfum'" class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-bold text-pink-600 mb-2">Sweet Boo Roll</h3>
                        <p class="text-xl font-extrabold text-pink-700 mb-4">Rp 7.500</p>
                        <p class="text-gray-600 mb-6">Manis, segar, dan menggemaskan! Campuran buah dan permen yang membuat Anda terasa muda dan ceria sepanjang hari.</p>
                        <button onclick="addToCart({id: 'sweetboo', name: 'Sweet Boo Roll', price: 7500})" class="cta-button w-full bg-pink-500 text-white font-bold py-3 rounded-full">
                            Pesan Sekarang!
                        </button>
                    </div>
                </div>

                <!-- Produk 3: Vanilla Cake Roll --><div class="bg-white rounded-xl shadow-2xl overflow-hidden hover:shadow-pink-400 transition duration-500">
                    <img src="https://p16-oec-sg.ibyteimg.com/tos-alisg-i-aphluv4xwc-sg/72a664625a6d427da876d23c1c1c6ca0~tplv-aphluv4xwc-resize-webp:526:525.webp?dr=15592&t=555f072d&ps=933b5bde&shp=8dbd94bf&shcp=e1be8f53&idc=my&from=2378011839" alt="Vanilla Cake Roll Parfum" onerror="this.onerror=null;this.src='https://placehold.co/400x400/FFFACD/333?text=Vanilla+Cake+Roll+Parfum'" class="w-full h-64 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-bold text-pink-600 mb-2">Vanilla Cake Roll</h3>
                        <p class="text-xl font-extrabold text-pink-700 mb-4">Rp 8.000</p>
                        <p class="text-gray-600 mb-6">Kehangatan kue vanilla yang baru dipanggang. Wangi yang lembut, nyaman, dan membuat orang ingin dekat. Seperti pelukan manis!</p>
                        <button onclick="addToCart({id: 'vanillacake', name: 'Vanilla Cake Roll', price: 8000})" class="cta-button w-full bg-pink-500 text-white font-bold py-3 rounded-full">
                            Pesan Sekarang!
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Bagian Tentang Kami --><section id="tentang" class="bg-pink-200 py-16">
            <div class="container mx-auto px-4 max-w-4xl text-center">
                <h2 class="text-4xl font-bold text-pink-700 mb-6">Tentang flowerss parfum</h2>
                <p class="text-gray-700 text-lg mb-4">flowerss parfum lahir dari kecintaan akan aroma yang membangkitkan mood. Kami percaya bahwa wewangian adalah sentuhan akhir terbaik untuk penampilan Anda. Semua parfum roll kami dibuat dengan hati-hati, memastikan kualitas wangi yang tahan lama dan harga yang terjangkau.</p>
                <p class="text-gray-700 text-lg font-semibold">Misi kami: Membuat setiap momen Anda semakin wangi dan menarik!</p>
            </div>
        </section>

        <!-- Bagian Testimoni --><section id="testimoni" class="py-16">
            <div class="container mx-auto px-4">
                <h2 class="text-4xl font-bold text-center text-pink-700 mb-12">Kata Mereka Tentang Kami</h2>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <!-- Testimoni 1 --><div class="bg-white p-6 rounded-xl shadow-xl border-t-4 border-pink-500">
                        <p class="text-gray-600 italic mb-4">"Nagita Roll bener-bener wangi mahal! Padahal harganya ramah di kantong. Selalu jadi andalan buat kerja, bikin pede!"</p>
                        <p class="font-semibold text-pink-600">- Maya S.</p>
                    </div>
                    <!-- Testimoni 2 --><div class="bg-white p-6 rounded-xl shadow-xl border-t-4 border-pink-500">
                        <p class="text-gray-600 italic mb-4">"Sweet Boo ini wanginya ceria banget! Kayak permen, suka! Pengiriman cepat dan adminnya responsif. Recommended!"</p>
                        <p class="font-semibold text-pink-600">- Rian A.</p>
                    </div>
                    <!-- Testimoni 3 --><div class="bg-white p-6 rounded-xl shadow-xl border-t-4 border-pink-500">
                        <p class="text-gray-600 italic mb-4">"Vanilla Cake Roll! Aroma kue yang bikin nyaman dan hangat. Nggak lengket di kulit. Terima kasih Isty Parfum!"</p>
                        <p class="font-semibold text-pink-600">- Dini P.</p>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Modal Keranjang & Checkout --><div id="cart-modal" class="fixed inset-0 hidden items-center justify-center modal-overlay transition-opacity duration-300 opacity-0">
        <div class="bg-white rounded-xl shadow-2xl w-full max-w-4xl p-6 md:p-10 modal-content transform opacity-0">
            <div class="flex justify-between items-center mb-6 border-b pb-4">
                <h3 class="text-3xl font-bold text-pink-700">Keranjang Belanja</h3>
                <button onclick="closeModal('cart-modal')" class="text-gray-400 hover:text-gray-600 text-3xl">&times;</button>
            </div>

            <!-- Detail Keranjang --><div id="cart-details" class="space-y-4 mb-6 max-h-60 overflow-y-auto">
                <p id="empty-cart-message" class="text-gray-500 text-center">Keranjang Anda kosong.</p>
            </div>

            <!-- Total Harga --><div class="border-t pt-4 flex justify-between items-center text-xl font-bold text-pink-700">
                <span>Total:</span>
                <span id="cart-total">Rp 0</span>
            </div>

            <!-- Formulir Checkout --><form id="checkout-form" class="mt-8 space-y-4">
                <h4 class="text-2xl font-bold text-pink-600 mb-4 border-b pb-2">Informasi Pengiriman</h4>
                <div>
                    <label for="customer-name" class="block text-sm font-medium text-gray-700">Nama Lengkap</label>
                    <input type="text" id="customer-name" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 border focus:border-pink-500 focus:ring-pink-500">
                </div>
                <div>
                    <label for="customer-address" class="block text-sm font-medium text-gray-700">Alamat Lengkap (Termasuk Kecamatan/Kota)</label>
                    <textarea id="customer-address" rows="3" required class="mt-1 block w-full rounded-md border-gray-300 shadow-sm p-3 border focus:border-pink-500 focus:ring-pink-500"></textarea>
                </div>

                <h4 class="text-2xl font-bold text-pink-600 mb-4 pt-4 border-t">Metode Pembayaran</h4>
                <div class="space-y-2">
                    <!-- Opsi Pembayaran --><div class="flex items-center">
                        <input type="radio" id="pay-dana" name="payment-method" value="DANA/GoPay/OVO/ShopeePay" class="h-4 w-4 text-pink-600 border-gray-300" checked onchange="toggleQrisDisplay(false)">
                        <label for="pay-dana" class="ml-3 text-sm font-medium text-gray-700">E-Wallet (DANA, GoPay, OVO, ShopeePay)</label>
                    </div>
                    <div class="flex items-center">
                        <input type="radio" id="pay-qris" name="payment-method" value="QRIS DANA" class="h-4 w-4 text-pink-600 border-gray-300" onchange="toggleQrisDisplay(true)">
                        <label for="pay-qris" class="ml-3 text-sm font-medium text-gray-700">QRIS (Scan Barcode)</label>
                    </div>
                    <div class="flex items-center">
                        <input type="radio" id="pay-cod" name="payment-method" value="Cash On Delivery (COD)" class="h-4 w-4 text-pink-600 border-gray-300" onchange="toggleQrisDisplay(false)">
                        <label for="pay-cod" class="ml-3 text-sm font-medium text-gray-700">Cash / Bayar di Tempat (COD)</label>
                    </div>
                </div>

                <!-- Tampilan QRIS (Conditional) --><div id="qris-display" class="hidden text-center bg-pink-50 p-6 rounded-lg border border-pink-200 mt-4">
                    <p class="text-lg font-bold text-pink-700 mb-4">SCAN BARCODE QRIS DI BAWAH INI</p>
                    <!-- Menggunakan placeholder QRIS yang menunjuk ke link DANA --><img src="https://placehold.co/300x300/4CAF50/FFFFFF?text=SCAN+QRIS+DANA"
                         alt="QRIS Code for DANA Payment"
                         class="mx-auto rounded-lg border-4 border-white shadow-xl">
                    <p class="text-xs text-gray-500 mt-2">QRIS ini mengarah ke tautan DANA: `https://link.dana.id/minta?...`</p>
                </div>

                <!-- Tombol Konfirmasi Pesanan --><button type="submit" id="confirm-order-btn" class="cta-button w-full bg-pink-500 text-white font-bold py-3 rounded-full mt-6" disabled>
                    Konfirmasi Pesanan via WhatsApp
                </button>
                <div id="error-message" class="text-red-500 mt-2 text-center hidden"></div>
            </form>

        </div>
    </div>

    <!-- Footer --><footer class="bg-pink-700 py-6 mt-16 shadow-inner relative z-10">
        <div class="container mx-auto text-center px-4">
            <p class="text-white text-3xl font-pacifico">
                Isty parfum — Teman Wangi mu!
            </p>
            <p class="text-pink-200 text-sm mt-2">&copy; 2025 flowerss parfum. All rights reserved.</p>
        </div>
    </footer>


    <script>
        // Data Produk
        const products = {
            'nagita': { name: 'Nagita Roll', price: 7000 },
            'sweetboo': { name: 'Sweet Boo Roll', price: 7500 },
            'vanillacake': { name: 'Vanilla Cake Roll', price: 8000 },
        };

        // State Keranjang
        let cart = [];

        // Admin WhatsApp Number
        const adminWhatsapp = '6285891693186';
        const qrisDanaLink = 'https://link.dana.id/minta?full_url=https://qr.dana.id/v1/281012012024110773006713';

        // Fungsi Helper untuk format mata uang IDR
        const formatRupiah = (number) => {
            return new Intl.NumberFormat('id-ID', {
                style: 'currency',
                currency: 'IDR',
                minimumFractionDigits: 0
            }).format(number);
        };

        // --- Logic Keranjang ---

        function updateCartDisplay() {
            const cartDetails = document.getElementById('cart-details');
            const cartTotalEl = document.getElementById('cart-total');
            const cartCountEl = document.getElementById('cart-count');
            const emptyMsgEl = document.getElementById('empty-cart-message');
            const confirmBtn = document.getElementById('confirm-order-btn');

            // Hitung Total
            let total = 0;
            let totalItems = 0;

            // Kosongkan dan isi ulang detail keranjang
            cartDetails.innerHTML = '';

            if (cart.length === 0) {
                emptyMsgEl.style.display = 'block';
                confirmBtn.disabled = true;
            } else {
                emptyMsgEl.style.display = 'none';
                confirmBtn.disabled = false;

                cart.forEach((item, index) => {
                    const itemTotal = item.price * item.quantity;
                    total += itemTotal;
                    totalItems += item.quantity;

                    const itemEl = document.createElement('div');
                    itemEl.className = 'flex justify-between items-center bg-pink-50 p-3 rounded-lg';
                    itemEl.innerHTML = `
                        <div class="flex-grow">
                            <span class="font-semibold text-pink-600">${item.name}</span>
                            <span class="text-sm text-gray-500"> (${formatRupiah(item.price)} x ${item.quantity})</span>
                        </div>
                        <div class="flex items-center space-x-2">
                            <button onclick="changeQuantity(${index}, -1)" class="text-pink-500 hover:text-pink-700 font-bold p-1">-</button>
                            <span class="font-bold w-4 text-center">${item.quantity}</span>
                            <button onclick="changeQuantity(${index}, 1)" class="text-pink-500 hover:text-pink-700 font-bold p-1">+</button>
                            <span class="font-bold w-24 text-right">${formatRupiah(itemTotal)}</span>
                        </div>
                    `;
                    cartDetails.appendChild(itemEl);
                });
            }

            cartTotalEl.textContent = formatRupiah(total);
            cartCountEl.textContent = totalItems > 99 ? '99+' : totalItems.toString();
        }

        function addToCart(product) {
            const existingItem = cart.find(item => item.id === product.id);

            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCartDisplay();
            openModal('cart-modal');
        }

        function changeQuantity(index, delta) {
            const item = cart[index];
            item.quantity += delta;

            if (item.quantity <= 0) {
                cart.splice(index, 1); // Hapus jika kuantitas 0 atau kurang
            }

            updateCartDisplay();
        }

        // --- Logic Modal & UI ---

        function openModal(modalId) {
            const modal = document.getElementById(modalId);
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            // Trigger transition
            setTimeout(() => {
                modal.classList.remove('opacity-0');
            }, 10);
        }

        function closeModal(modalId) {
            const modal = document.getElementById(modalId);
            modal.classList.add('opacity-0');
            // Hide modal after transition
            setTimeout(() => {
                modal.classList.remove('flex');
                modal.classList.add('hidden');
                toggleQrisDisplay(false); // Sembunyikan QRIS saat menutup
            }, 300);
        }

        function toggleQrisDisplay(show) {
            const qrisDisplay = document.getElementById('qris-display');
            if (show) {
                qrisDisplay.classList.remove('hidden');
            } else {
                qrisDisplay.classList.add('hidden');
            }
        }

        // --- Logic WhatsApp Order ---

        document.getElementById('checkout-form').addEventListener('submit', function(e) {
            e.preventDefault();

            const name = document.getElementById('customer-name').value;
            const address = document.getElementById('customer-address').value;
            const paymentMethod = document.querySelector('input[name="payment-method"]:checked').value;
            const totalElement = document.getElementById('cart-total');
            const totalText = totalElement.textContent;

            if (cart.length === 0) {
                document.getElementById('error-message').textContent = 'Keranjang kosong. Tambahkan produk dulu!';
                document.getElementById('error-message').classList.remove('hidden');
                return;
            } else {
                document.getElementById('error-message').classList.add('hidden');
            }

            // Membangun detail pesanan
            let orderDetails = '';
            cart.forEach((item, index) => {
                const itemTotal = item.price * item.quantity;
                orderDetails += `${index + 1}. *${item.name}* (x${item.quantity}) - ${formatRupiah(itemTotal)}%0A`; // %0A adalah Newline di URL
            });

            // Membangun pesan WhatsApp
            const whatsappMessage = encodeURIComponent(
                `*--- flowerss parfum: PESANAN BARU ---*%0A%0A` +
                `*INFORMASI PELANGGAN:*%0A` +
                `Nama: ${name}%0A` +
                `Alamat: ${address}%0A%0A` +
                `*DETAIL PESANAN:*%0A` +
                `${orderDetails}%0A` +
                `*TOTAL HARGA:* ${totalText}%0A%0A` +
                `*METODE PEMBAYARAN:* ${paymentMethod}%0A%0A` +
                `Terima kasih atas pesanannya! Mohon diproses.`
            );

            const whatsappUrl = `https://wa.me/${adminWhatsapp}?text=${whatsappMessage}`;

            // Reset Keranjang dan Form
            cart = [];
            updateCartDisplay();
            this.reset();
            closeModal('cart-modal');
            
            // Arahkan ke WhatsApp
            window.open(whatsappUrl, '_blank');
        });

        // --- Inisialisasi ---

        // Fungsi untuk men-generate bunga jatuh secara dinamis
        function generateFlowers() {
            const flowerContainer = document.querySelector('.flower-container');
            const flowerChars = ['🌸', '🌼', '🌺', '🌷', '🏵️'];
            const flowerCount = 30; // Jumlah bunga

            for (let i = 0; i < flowerCount; i++) {
                const flower = document.createElement('span');
                flower.className = 'flower';
                flower.textContent = flowerChars[Math.floor(Math.random() * flowerChars.length)];
                
                // Posisi dan waktu acak
                flower.style.left = `${Math.random() * 100}vw`;
                flower.style.animationDuration = `${10 + Math.random() * 10}s`; // Durasi 10-20s
                flower.style.animationDelay = `${Math.random() * 20}s`; // Delay 0-20s
                flower.style.opacity = '0'; // Mulai dengan opacity 0
                flower.style.fontSize = `${1 + Math.random() * 1.5}rem`; // Ukuran 1rem - 2.5rem

                flowerContainer.appendChild(flower);
            }
        }

        window.onload = function() {
            updateCartDisplay(); // Tampilkan keranjang kosong saat pertama kali
            generateFlowers(); // Mulai animasi bunga
        };
    </script>

</body>
</html>
