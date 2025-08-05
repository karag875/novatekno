<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NovaTekno - Alışverişin Yeni Adı</title>
  <link rel="icon" type="image/png" href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Home-icon.svg/64px-Home-icon.svg.png">
  <style>
    * { box-sizing: border-box; }
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: linear-gradient(to right, #f5f7fa, #c3cfe2);
      color: #333;
    }
    header {
      background: linear-gradient(to right, #003973, #e5e5be);
      color: white;
      padding: 1rem 2rem;
    }
    header h1 { margin: 0; font-size: 2rem; }
    header p { margin: 0.2rem 0 0; font-size: 1rem; }

    nav {
      background: linear-gradient(to right, #fc466b, #3f5efb);
      padding: 1rem;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
      border-bottom: 2px solid #fff;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: 0.3s;
    }
    nav a:hover {
      text-decoration: underline;
    }

    .topbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: #fefefe;
      padding: 0.5rem 2rem;
      border-bottom: 1px solid #ccc;
    }
    .topbar input {
      margin-right: 0.5rem;
      padding: 0.3rem;
    }
    .topbar button {
      background: linear-gradient(to right, #ff9966, #ff5e62);
      color: white;
      border: none;
      padding: 0.4rem 0.8rem;
      border-radius: 4px;
      cursor: pointer;
      font-weight: bold;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
      padding: 2rem;
    }
    .product {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: transform 0.3s;
    }
    .product:hover {
      transform: scale(1.03);
    }
    .product button {
      background: linear-gradient(to right, #00b09b, #96c93d);
      color: white;
      border: none;
      padding: 0.6rem 1.2rem;
      cursor: pointer;
      border-radius: 5px;
      font-weight: bold;
    }

    .section {
      background: white;
      margin: 2rem;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }

    .admin-panel {
      background: #fff3cd;
      border: 1px solid #ffeeba;
      padding: 1.5rem;
      margin: 2rem;
      border-radius: 8px;
      display: none;
    }

    .admin-visible .admin-panel {
      display: block;
    }

    footer {
      background: linear-gradient(to right, #000428, #004e92);
      color: white;
      text-align: center;
      padding: 2rem;
    }
    footer img {
      height: 40px;
      margin: 0.5rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>NovaTekno</h1>
    <p>Türkiye'nin Teknoloji ve Alışveriş Merkezi</p>
  </header>

  <div class="topbar">
    <div>
      <input type="text" id="username" placeholder="Kullanıcı Adı">
      <input type="password" id="password" placeholder="Şifre">
      <button onclick="login()">Giriş</button>
      <button>Üye Ol</button>
    </div>
    <div>
      <button>🛒 Sepet</button>
    </div>
  </div>

  <nav>
    <a href="#urunler">Ürünler</a>
    <a href="#kampanyalar">Kampanyalar</a>
    <a href="#kredi">Kredi</a>
    <a href="#sss">SSS</a>
    <a href="#hakkimizda">Hakkımızda</a>
  </nav>

  <section class="products" id="urunler">
    <div class="product">
      <h3>Akıllı Telefon</h3>
      <p>128GB, 6GB RAM</p>
      <strong>₺8.999</strong>
      <button>Sepete Ekle</button>
    </div>
    <div class="product">
      <h3>Dizüstü Bilgisayar</h3>
      <p>i7, 16GB RAM, 512GB SSD</p>
      <strong>₺19.999</strong>
      <button>Sepete Ekle</button>
    </div>
    <div class="product">
      <h3>Bluetooth Kulaklık</h3>
      <p>Su geçirmez, uzun pil ömrü</p>
      <strong>₺799</strong>
      <button>Sepete Ekle</button>
    </div>
  </section>

  <section class="section" id="kampanyalar">
    <h2>Kampanyalar</h2>
    <ul>
      <li>3 al 2 öde</li>
      <li>Peşin fiyatına 6 taksit</li>
      <li>Kredi kartı puanlarına özel indirimler</li>
    </ul>
  </section>

  <section class="section" id="kredi">
    <h2>Kredi Başvurusu</h2>
    <form onsubmit="submitApplication(event)">
      <input type="text" placeholder="Ad Soyad" id="adsoyad" required><br><br>
      <input type="text" placeholder="T.C. Kimlik No" id="tcno" required><br><br>
      <input type="date" id="dogumtarihi" required><br><br>
      <button type="submit">Başvur</button>
    </form>
    <ul id="adminApplications" style="margin-top:2rem;"></ul>
  </section>

  <section class="section" id="sss">
    <h2>Sık Sorulan Sorular</h2>
    <p><strong>Kargo Süresi:</strong> Siparişleriniz 1-3 iş günü içinde kargoya verilir.</p>
    <p><strong>İade Koşulları:</strong> 14 gün içinde koşulsuz iade hakkı.</p>
  </section>

  <section class="section" id="hakkimizda">
    <h2>Hakkımızda</h2>
    <p>NovaTekno, teknolojiyi herkes için erişilebilir kılmayı hedefleyen yenilikçi bir e-ticaret platformudur.</p>
  </section>

  <section class="admin-panel" id="admin">
    <h2>Admin Paneli</h2>
    <p>Buradan kredi başvurularını ve kullanıcıları yönetebilirsiniz.</p>
    <ul>
      <li>Yeni başvurular: <span id="basvuruSayisi">0</span> adet</li>
      <li>Yeni üyelikler: 5 kullanıcı</li>
      <li>Toplam satış: ₺82.300</li>
    </ul>
  </section>

  <footer>
    <p>İletişim: info@novatekno.com | 0 (555) 123 45 67</p>
    <div>
      <h4>Çalıştığımız Bankalar</h4>
      <img src="https://upload.wikimedia.org/wikipedia/commons/8/89/Ziraat_Bank_logo.png" alt="Ziraat">
      <img src="https://upload.wikimedia.org/wikipedia/commons/d/da/Vak%C4%B1fBank_logo_2021.png" alt="VakıfBank">
      <img src="https://upload.wikimedia.org/wikipedia/tr/0/0b/Halkbank_logo_yeni.png" alt="Halkbank">
      <img src="https://upload.wikimedia.org/wikipedia/en/thumb/6/6f/QNB_Finansbank_logo.svg/512px-QNB_Finansbank_logo.svg.png" alt="QNB">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/T%C3%BCrkiye_%C4%B0%C5%9F_Bankas%C4%B1_logo.svg/320px-T%C3%BCrkiye_%C4%B0%C5%9F_Bankas%C4%B1_logo.svg.png" alt="İş Bankası">
      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6f/Novapay_logo.png" alt="NovaPay">
    </div>
    <p>&copy; 2025 NovaTekno - Tüm hakları saklıdır.</p>
  </footer>

  <script>
    function login() {
      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;
      if (username === 'admin' && password === 'admin123') {
        document.body.classList.add('admin-visible');
        alert('Admin girişi başarılı. Admin paneli açıldı.');
      } else {
        alert('Giriş başarılı (demo).');
      }
    }

    function submitApplication(event) {
      event.preventDefault();
      const ad = document.getElementById('adsoyad').value;
      const tc = document.getElementById('tcno').value;
      const dogum = document.getElementById('dogumtarihi').value;

      const ul = document.getElementById('adminApplications');
      const li = document.createElement('li');

      li.innerHTML = `
        <strong>${ad}</strong> - T.C: ${tc} - Doğum: ${dogum} <br>
        Limit Belirle: <input type="number" placeholder="₺" style="width:100px;"> 
        <button onclick="this.previousElementSibling.disabled = true; this.disabled = true; alert('Limit uygulandı.')">Onayla</button>
      `;

      ul.appendChild(li);
      document.getElementById('basvuruSayisi').textContent = ul.children.length;
    }
  </script>
</body>
</html>
