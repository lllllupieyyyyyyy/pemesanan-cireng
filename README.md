# pemesanan cireng
<html lang="id">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no" />
<title>Pemesanan Cireng</title>
<style>
  /* Reset and base */
  * {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #f6d365 0%, #fda085 100%);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    padding: 15px;
    color: #3e3e3e;
  }
  .container {
    background: #fff;
    border-radius: 12px;
    box-shadow: 0 8px 24px rgba(0,0,0,0.16);
    max-width: 350px;
    width: 100%;
    padding: 25px 30px 30px 30px;
    transition: transform 0.3s ease;
  }
  .container:focus-within {
    transform: scale(1.02);
  }
  h1 {
    font-weight: 900;
    text-align: center;
    color: #d73035;
    font-size: 2.4rem;
    margin-bottom: 6px;
    letter-spacing: 1.2px;
    user-select: none;
  }
  p.subtitle {
    text-align: center;
    color: #6d6d6d;
    font-size: 15px;
    margin-top: 0;
    margin-bottom: 28px;
    font-weight: 600;
  }
  form label {
    display: block;
    margin-bottom: 6px;
    font-weight: 700;
    font-size: 16px;
    color: #444;
  }
  fieldset {
    border: none;
    margin-bottom: 22px;
  }
  legend {
    font-weight: 800;
    font-size: 18px;
    color: #d73035;
    margin-bottom: 14px;
    border-bottom: 2px solid #f9a49a;
    padding-bottom: 6px;
    user-select: none;
  }
  .menu-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    font-weight: 700;
    font-size: 17px;
    color: #3e3e3e;
    user-select: none;
  }
  .menu-item small {
    display: block;
    color: #888;
    font-weight: 400;
    font-size: 13px;
    margin-top: 2px;
  }
  .qty-controls {
    display: flex;
    align-items: center;
  }
  .qty-controls button {
    background: #d73035;
    border: none;
    color: white;
    font-weight: 900;
    font-size: 23px;
    width: 36px;
    height: 36px;
    border-radius: 8px;
    cursor: pointer;
    user-select: none;
    transition: background-color 0.25s ease;
  }
  .qty-controls button:disabled {
    background: #f8b9b4;
    cursor: not-allowed;
  }
  .qty-controls button:hover:not(:disabled) {
    background: #ba2a2a;
  }
  .qty-controls input {
    width: 45px;
    text-align: center;
    border: 2px solid #d73035;
    border-radius: 8px;
    margin: 0 8px;
    font-size: 18px;
    font-weight: 900;
    color: #d73035;
    -moz-appearance: textfield;
    padding: 3px 0;
  }
  input[type="text"], input[type="tel"], select {
    width: 100%;
    padding: 10px 14px;
    margin-bottom: 18px;
    border-radius: 10px;
    border: 2px solid #d73035;
    font-size: 17px;
    font-weight: 600;
    outline-offset: 3px;
    outline-color: #f9a49a;
    transition: border-color 0.3s ease;
    user-select: text;
  }
  input[type="text"]:focus, input[type="tel"]:focus, select:focus {
    border-color: #a1211d;
  }
  .radio-group {
    margin-bottom: 18px;
  }
  .radio-group label {
    font-weight: 700;
    font-size: 15px;
    margin-right: 24px;
    cursor: pointer;
    user-select: none;
  }
  .radio-group input {
    margin-right: 8px;
    cursor: pointer;
  }
  .total-display {
    text-align: right;
    font-weight: 900;
    font-size: 20px;
    color: #d73035;
    margin-bottom: 25px;
    border-top: 3px solid #f9a49a;
    padding-top: 14px;
    user-select: none;
  }
  button.submit-btn {
    background: #d73035;
    border: none;
    color: white;
    width: 100%;
    font-weight: 900;
    font-size: 20px;
    padding: 14px 0;
    border-radius: 14px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    user-select: none;
    box-shadow: 0 6px 14px rgba(215, 48, 53, 0.55);
  }
  button.submit-btn:hover,
  button.submit-btn:focus {
    background: #ab2629;
    outline: none;
    box-shadow: 0 8px 18px rgba(171, 38, 41, 0.7);
  }
  button.submit-btn:active {
    transform: scale(0.97);
  }
  .confirmation {
    margin-top: 22px;
    background: #dff0d8;
    color: #3c763d;
    border-radius: 12px;
    padding: 16px 20px;
    font-weight: 700;
    font-size: 16px;
    display: none;
    white-space: pre-wrap;
    user-select: text;
    box-shadow: inset 0 0 14px #a4d188;
    text-align: center;
  }
  @media (max-width: 400px) {
    body {
      padding: 10px;
    }
    .container {
      padding: 22px 22px 26px 22px;
    }
    h1 {
      font-size: 2rem;
    }
    .menu-item {
      font-size: 15px;
    }
    .qty-controls button,
    .qty-controls input {
      width: 32px;
      height: 32px;
      font-size: 20px;
      margin: 0 6px;
    }
    button.submit-btn {
      font-size: 18px;
      padding: 12px 0;
    }
    .confirmation {
      font-size: 14px;
      padding: 14px 16px;
    }
  }
</style>
</head>
<body>
  <main class="container" role="main" aria-label="Formulir Pemesanan Cireng">
    <h1>Pemesanan Cireng</h1>
    <p class="subtitle" id="subtitle">Pilih dan pesan cireng favoritmu!</p>
    <form id="orderForm" novalidate aria-describedby="subtitle">
      <fieldset>
        <legend>Menu Cireng</legend>
        <div class="menu-item" data-price="2000" data-name="Cireng Keju 3pcs">
          <div>
            Cireng Keju 3pcs<br />
            <small>Rp 2.000</small>
          </div>
          <div class="qty-controls" role="group" aria-label="Jumlah Cireng Keju 3pcs">
            <button type="button" class="qty-minus" aria-label="Kurangi jumlah Cireng Keju">−</button>
            <input type="number" class="qty-input" min="0" max="99" value="0" aria-live="polite" aria-label="Jumlah Cireng Keju" inputmode="numeric" pattern="[0-9]*" />
            <button type="button" class="qty-plus" aria-label="Tambah jumlah Cireng Keju">+</button>
          </div>
        </div>
        <div class="menu-item" data-price="2000" data-name="Cireng Ayam Suwir 3pcs">
          <div>
            Cireng Ayam Suwir 3pcs<br />
            <small>Rp 2.000</small>
          </div>
          <div class="qty-controls" role="group" aria-label="Jumlah Cireng Ayam Suwir 3pcs">
            <button type="button" class="qty-minus" aria-label="Kurangi jumlah Cireng Ayam Suwir">−</button>
            <input type="number" class="qty-input" min="0" max="99" value="0" aria-live="polite" aria-label="Jumlah Cireng Ayam Suwir" inputmode="numeric" pattern="[0-9]*" />
            <button type="button" class="qty-plus" aria-label="Tambah jumlah Cireng Ayam Suwir">+</button>
          </div>
        </div>
      </fieldset>

      <fieldset>
        <legend>Data Pemesan</legend>
        <label for="nama">Nama Pemesan<span aria-hidden="true" style="color:#d73035;"> *</span></label>
        <input type="text" id="nama" name="nama" placeholder="Masukkan nama Anda" required autocomplete="name" aria-required="true" />
        <label for="hp">Nomor HP<span aria-hidden="true" style="color:#d73035;"> *</span></label>
        <input type="tel" id="hp" name="hp" placeholder="Masukkan nomor HP" pattern="^08[0-9]{8,12}$" title="Nomor HP harus diawali dengan 08, 10-14 digit" required autocomplete="tel" aria-required="true" inputmode="tel" />
      </fieldset>

      <fieldset>
        <legend>Opsi Pembayaran</legend>
        <div class="radio-group" role="radiogroup" aria-label="Opsi pembayaran">
          <label><input type="radio" name="pembayaran" value="Tunai" checked required aria-checked="true" /> Tunai</label>
        </div>
      </fieldset>

      <fieldset>
        <legend>Opsi Pengiriman</legend>
        <div class="radio-group" role="radiogroup" aria-label="Opsi pengiriman">
          <label><input type="radio" name="pengiriman" value="Pick Up" checked required aria-checked="true" /> Pick Up</label>
        </div>
      </fieldset>

      <p class="total-display" aria-live="polite" id="totalDisplay">Total Pesanan: Rp 0</p>

      <button type="submit" class="submit-btn" aria-label="Kirim pesanan sekarang">Pesan Sekarang</button>
    </form>
    <section class="confirmation" id="confirmation" role="alert" aria-live="assertive"></section>
  </main>

<script>
document.addEventListener('DOMContentLoaded', () => {
  const form = document.getElementById('orderForm');
  const totalDisplay = document.getElementById('totalDisplay');
  const menuItems = form.querySelectorAll('.menu-item');
  const confirmationEl = document.getElementById('confirmation');

  // Utility: Format number as Indonesian Rupiah
  function formatRupiah(number) {
    return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', minimumFractionDigits: 0 }).format(number);
  }

  function updateTotal() {
    let total = 0;
    menuItems.forEach(item => {
      const price = parseInt(item.dataset.price, 10);
      const qtyInput = item.querySelector('.qty-input');
      const qty = Number(qtyInput.value) || 0;
      total += price * qty;
    });
    totalDisplay.textContent = `Total Pesanan: ${formatRupiah(total)}`;
    return total;
  }

  menuItems.forEach(item => {
    const minusBtn = item.querySelector('.qty-minus');
    const plusBtn = item.querySelector('.qty-plus');
    const qtyInput = item.querySelector('.qty-input');

    minusBtn.addEventListener('click', () => {
      let current = Number(qtyInput.value) || 0;
      if (current > Number(qtyInput.min)) {
        qtyInput.value = current - 1;
        updateTotal();
      }
    });

    plusBtn.addEventListener('click', () => {
      let current = Number(qtyInput.value) || 0;
      if (current < Number(qtyInput.max)) {
        qtyInput.value = current + 1;
        updateTotal();
      }
    });

    qtyInput.addEventListener('input', () => {
      let val = Number(qtyInput.value);
      if (isNaN(val) || val < Number(qtyInput.min)) {
        qtyInput.value = qtyInput.min;
      } else if (val > Number(qtyInput.max)) {
        qtyInput.value = qtyInput.max;
      }
      updateTotal();
    });

    qtyInput.addEventListener('keypress', (e) => {
      // Only allow digits
      const char = String.fromCharCode(e.which);
      if (!/[0-9]/.test(char)) {
        e.preventDefault();
      }
    });
  });

  form.addEventListener('submit', (e) => {
    e.preventDefault();
    confirmationEl.style.display = 'none';
    confirmationEl.textContent = '';

    const nama = form.nama.value.trim();
    const hp = form.hp.value.trim();
    const pembayaran = form.pembayaran.value;
    const pengiriman = form.pengiriman.value;
    const total = updateTotal();

    if (!nama) {
      alert("Mohon isi Nama Pemesan.");
      form.nama.focus();
      return;
    }
    const hpPattern = /^08[0-9]{8,12}$/;
    if (!hpPattern.test(hp)) {
      alert("Nomor HP tidak valid. Harus diawali dengan 08 dan panjang 10-14 digit.");
      form.hp.focus();
      return;
    }
    if (total === 0) {
      alert("Silakan pilih minimal satu menu cireng untuk dipesan.");
      return;
    }

    let orderList = '';
    menuItems.forEach(item => {
      const name = item.dataset.name;
      const qty = Number(item.querySelector('.qty-input').value) || 0;
      if (qty > 0) {
        orderList += `${qty} x ${name}\n`;
      }
    });

    const orderSummary = 
      `Terima kasih, ${nama}!\n\n` +
      `Detail Pesanan Anda:\n${orderList}\n` +
      `Total: ${formatRupiah(total)}\n` +
      `Pembayaran: ${pembayaran}\n` +
      `Pengiriman: ${pengiriman}\n\n` +
      `Pesanan akan segera kami proses.`;

    // Show alert
    alert(orderSummary);

    // Also show confirmation below form
    confirmationEl.textContent = orderSummary;
    confirmationEl.style.display = 'block';

    form.reset();
    updateTotal();
  });

  updateTotal();
});
</script>
</body>
</html>
