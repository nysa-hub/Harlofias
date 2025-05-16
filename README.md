<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Harlofias - Nisa Bilmez ile İçsel Keşifler</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=DM+Serif+Display:ital@0;1&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #D6E6FD; /* Yeni: Açık Mavi */
            --text-color: #4A4F87; /* Yeni: Koyu Mavi/Mor */
            --heading-color: #0f0b5a; /* Yeni: Çok Koyu Mavi */
            --link-hover-color: #C41E4E; /* Yeni: Koyu Pembe/Kırmızı */
            --btn-pink: rgb(226, 122, 240); /* Yeni: Parlak Pembe/Mor */
            --btn-blue: #ADD8E6; /* Bu aynı kalabilir veya temaya uydurulabilir */
            --btn-yellow: #FFFACD; /* Bu aynı kalabilir veya temaya uydurulabilir */
            --border-color: rgba(74, 79, 135, 0.25); /* Yeni: text-color'dan türetilmiş */

            --font-body: 'Cormorant Garamond', serif;
            --font-heading: 'Playfair Display', serif;
            --font-special: 'DM Serif Display', serif;
        }

        *, *::before, *::after { box-sizing: border-box; }

        body {
            background-color: var(--bg-color); color: var(--text-color); font-family: var(--font-body);
            margin: 0; padding: 0; line-height: 1.9; font-size: 19px;
            font-weight: 400; overflow-x: hidden;
            -webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale;
        }

        .container { max-width: 850px; margin: 0 auto; padding: 0 20px; }

        header {
            display: flex; justify-content: space-between; align-items: center;
            padding: 40px 0; border-bottom: 1px solid var(--border-color); margin-bottom: 30px;
        }
        .logo a {
            font-family: var(--font-special); font-size: 2.9em; color: var(--heading-color);
            text-decoration: none; font-weight: normal;
        }
        nav ul { list-style: none; display: flex; padding: 0; margin: 0; }
        nav ul li { margin-left: 35px; }
        nav ul li a {
            font-family: var(--font-heading); text-decoration: none; color: var(--text-color);
            font-size: 1.18em; font-weight: 500; padding-bottom: 6px; position: relative;
            transition: color 0.3s ease;
        }
        nav ul li a::after {
            content: ''; position: absolute; width: 0; height: 2px; bottom: 0; left: 50%;
            transform: translateX(-50%); background-color: var(--heading-color); transition: width 0.3s ease;
        }
        nav ul li a:hover, nav ul li a.active { color: var(--heading-color); }
        nav ul li a.active::after { width: 100%; }

        #content-area { padding: 20px 0 40px; min-height: 60vh; }
        .content-section { display: none; opacity: 0; animation: fadeIn 0.8s ease-out forwards; }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .content-section.active { display: block; }

        .content-section h1, .content-section h2, .content-section h3 {
            font-family: var(--font-heading); color: var(--heading-color);
            font-weight: 700; margin-top: 0;
        }
        .content-section h1 { font-size: 2.6em; margin-bottom: 35px; text-align: center;}
        .content-section h2 { font-size: 2em; margin-bottom: 25px; margin-top: 45px; }
        .content-section h3 { font-size: 1.6em; margin-bottom: 18px; color: var(--text-color); font-weight: 600;}
        .content-section p { margin-bottom: 22px; font-size: 1.08em; }
        .content-section strong { font-weight: 600; }
        .content-section blockquote {
            border-left: 3px solid var(--heading-color);
            margin-left: 0; margin-right: 0; padding-left: 20px;
            font-style: italic; font-size: 1.1em; color: var(--text-color); opacity: 0.9;
            margin-bottom: 22px;
        }
        .content-section ul, .content-section ol { padding-left: 30px; margin-bottom: 22px;}
        .content-section li { margin-bottom: 8px; }

        .content-section a:not(.button) {
            color: var(--heading-color); text-decoration: none;
            border-bottom: 1px dotted var(--heading-color);
            transition: color 0.3s, border-bottom-color 0.3s; font-weight: 600;
        }
        .content-section a:not(.button):hover {
            color: var(--link-hover-color); border-bottom-color: var(--link-hover-color);
        }

        /* Profile Image Styling */
        .about-image-container {
            text-align: center; /* Resmi ortala */
            margin-bottom: 30px;
        }
        .profile-image {
            max-width: 220px; /* Fotoğrafın maksimum genişliği */
            width: 100%;
            height: auto;
            border-radius: 50%; /* Yuvarlak yapmak için */
            border: 5px solid #fff; /* İnce beyaz çerçeve */
            box-shadow: 0 5px 15px rgba(74, 79, 135, 0.2); /* Hafif gölge */
        }

        .diary-entry {
            margin-bottom: 60px; padding-bottom: 40px;
            border-bottom: 1px dashed var(--border-color);
        }
        .diary-entry:last-child { border-bottom: none; margin-bottom: 0; }
        .diary-entry .entry-date {
            font-family: var(--font-body); font-style: italic; color: var(--text-color);
            opacity: 0.8; font-size: 0.95em; margin-bottom: 12px; display: block;
        }
        .diary-entry h2 a { color: var(--heading-color); text-decoration: none; border-bottom: none; }
        .diary-entry h2 a:hover { color: var(--link-hover-color); }

        .shop-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; }
        .shop-item {
            background-color: #fff; border: 1px solid var(--border-color); border-radius: 8px;
            padding: 25px; display: flex; flex-direction: column; justify-content: space-between;
            box-shadow: 0 2px 5px rgba(74, 79, 135, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .shop-item:hover { transform: translateY(-5px); box-shadow: 0 5px 15px rgba(74, 79, 135, 0.15); }
        .shop-item .product-cover {
            width: 100%; height: 200px; background-color: rgba(255,255,255,0.5); /* Daha açık bir placeholder */
            margin-bottom: 20px;
            border-radius: 4px; display: flex; align-items: center; justify-content: center;
            font-family: var(--font-heading); color: var(--text-color); opacity: 0.7;
            font-size: 1.1em; text-align: center; padding: 10px;
            border: 1px dashed var(--border-color);
        }
        .shop-item h3 { margin-top: 0; font-size: 1.4em; color: var(--heading-color); }
        .shop-item .price { font-size: 1.3em; font-weight: 700; color: var(--text-color); margin: 15px 0; }

        .button {
            display: inline-block; padding: 12px 28px; border: 1.5px solid transparent;
            border-radius: 6px; font-family: var(--font-heading); font-size: 1.05em;
            font-weight: 500; text-decoration: none; cursor: pointer; margin-top: 15px;
            margin-right: 10px; margin-bottom: 10px; transition: all 0.3s ease;
            color: #fff; /* Buton metin rengi beyaz olabilir */
            text-align: center;
        }
        .button-pink { background-color: var(--btn-pink); color: var(--heading-color); /* Veya beyaz */ }
        .button-blue { background-color: var(--btn-blue); color: var(--heading-color); }
        .button-yellow { background-color: var(--btn-yellow); color: var(--heading-color); }
        .button:hover {
            opacity: 0.85;
            transform: translateY(-2px) scale(1.02);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }
        /* Butonların metin renklerini ve hover durumlarını yeni temaya göre ayarlayabilirsin */
        .button-pink:hover { background-color: darken(var(--btn-pink), 10%); }


        .contact-form { max-width: 600px; margin: 30px auto 0; }
        .contact-form .form-group { margin-bottom: 20px; }
        .contact-form label { display: block; margin-bottom: 8px; font-family: var(--font-heading); font-weight: 600; font-size: 1.05em; }
        .contact-form input[type="text"], .contact-form input[type="email"], .contact-form textarea {
            width: 100%; padding: 12px 15px; border: 1px solid var(--border-color);
            border-radius: 5px; background-color: #fff; font-family: var(--font-body);
            font-size: 1em; transition: border-color 0.3s ease; color: var(--text-color);
        }
        .contact-form input[type="text"]:focus, .contact-form input[type="email"]:focus, .contact-form textarea:focus {
            border-color: var(--heading-color); outline: none; box-shadow: 0 0 0 2px rgba(15, 11, 90, 0.2);
        }
        .contact-form textarea { min-height: 150px; resize: vertical; }

        footer {
            text-align: center; padding: 40px 0; font-size: 0.95em; color: var(--text-color);
            opacity: 0.8; border-top: 1px solid var(--border-color); margin-top: 50px;
        }
        footer p { margin: 5px 0; }

        @media (max-width: 768px) {
            body { font-size: 17px; line-height: 1.8; }
            .container { padding: 0 15px; }
            header { flex-direction: column; align-items: center; padding-bottom: 25px; margin-bottom: 20px; }
            .logo a { font-size: 2.5em; margin-bottom: 25px; }
            nav ul { justify-content: center; flex-wrap: wrap; }
            nav ul li { margin: 5px 15px; }
            nav ul li a { font-size: 1.1em; }
            .content-section h1 { font-size: 2.1em; margin-bottom: 25px;}
            .content-section h2 { font-size: 1.7em; }
            .shop-grid { grid-template-columns: 1fr; }
            .profile-image { max-width: 180px; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <a href="#diary">Harlofias</a>
            </div>
            <nav>
                <ul>
                    <li><a href="#diary" class="nav-link">Blog</a></li> 
                    <li><a href="#shop" class="nav-link">dükkan</a></li>
                    <li><a href="#about" class="nav-link">hakkımda</a></li>
                    <li><a href="#contact" class="nav-link">iletişim</a></li>
                </ul>
            </nav>
        </header>

        <main id="content-area">
            <!-- DIARY SECTION (Content from nisabilmez.com/yazilar) -->
            <section id="diary" class="content-section">
                <h1>Blog Yazıları</h1>

                <article class="diary-entry">
                    <span class="entry-date">28 Mayıs 2024</span>
                    <h2><a href="#">Kendi Hikayenin Kahramanı Olmak</a></h2>
                    <p>Hayat bir masalsa eğer ve bu masalda her birimiz kendi hikayemizin kahramanıysak, o zaman başrolde neden başkaları olsun ki? Neden kendi hikayemizi yazmak yerine, başkalarının yazdığı rolleri oynamaya çalışalım?</p>
                    <p>Çoğu zaman, farkında olmadan, toplumun, ailenin ya da çevrenin bize biçtiği rolleri üstleniriz. “İyi evlat” oluruz, “başarılı öğrenci” oluruz, “sadık eş” oluruz… Peki ya “kendimiz” olmayı ne zaman hatırlarız? Kendi iç sesimizi dinlemeyi, kendi hayallerimizin peşinden gitmeyi ne zaman öğreniriz?</p>
                    <p>Kendi hikayenin kahramanı olmak, cesaret ister. Toplumun dayattığı kalıpları kırmak, “elalem ne der?” korkusunu yenmek, kendi doğrularını savunmak… Tüm bunlar, içsel bir güç ve kararlılık gerektirir. Ama unutma, bu güç senin içinde zaten var. Tıpkı bir tohumun içinde kocaman bir ağacı barındırması gibi, senin de içinde keşfedilmeyi bekleyen sonsuz bir potansiyel yatıyor.</p>
                    <p>Kendi hikayenin kahramanı olmak, kendi değerlerini bilmekle başlar. Seni sen yapan nedir? Hayattaki önceliklerin neler? Hangi değerler uğruna mücadele edersin? Bu soruların cevaplarını bulduğunda, kendi yol haritanı çizmeye başlayabilirsin.</p>
                    <p>Unutma, bu yolculukta yalnız değilsin. Hepimiz zaman zaman kaybolur, zaman zaman sendeleriz. Önemli olan, her düştüğümüzde yeniden ayağa kalkabilmek, her hatadan ders çıkarabilmek ve her yeni güne umutla başlayabilmektir.</p>
                    <p>Kendi hikayenin kahramanı ol. Kendi masalını yaz. Ve unutma, en güzel masallar, cesur kahramanların kaleminden çıkar.</p>
                    <a href="#contact" class="button button-yellow">Yorum & Soru Bırak</a>
                </article>

                <article class="diary-entry">
                    <span class="entry-date">15 Mayıs 2024</span>
                    <h2><a href="#">Yavaşla, Dinle, Hisset: An’da Kalmanın Büyüsü</a></h2>
                    <p>Koşuşturmaca… Sürekli bir yerlere yetişme telaşı… Zihnimizde dönüp duran düşünceler… Modern hayatın hızı, bizi adeta bir girdap gibi içine çekiyor. Peki, bu girdabın içinde kaybolmamak, an’ın büyüsünü yakalamak mümkün mü?</p>
                    <p>Evet, mümkün. Ve bunun için ihtiyacımız olan tek şey, biraz yavaşlamak, içimize dönmek ve etrafımızdaki güzellikleri fark etmek.</p>
                    <p>An’da kalmak, zihnimizi geçmişin pişmanlıklarından ve geleceğin kaygılarından arındırıp, şimdiki anın farkındalığına odaklanmaktır. Bir çiçeğin kokusunu içine çekmek, bir kuşun cıvıltısını dinlemek, bir fincan kahvenin sıcaklığını hissetmek… İşte bunlar, an’da kalmanın küçük ama etkili adımlarıdır.</p>
                    <p>Yavaşlamak, hayatın hızına bir mola vermek, kendimize nefes alacak alanlar yaratmaktır. Her gün sadece birkaç dakikanızı ayırarak, sessiz bir köşede oturup derin nefesler alabilir, düşüncelerinizi gözlemleyebilir ve bedeninizi dinleyebilirsiniz. Bu küçük molalar, zihninizi sakinleştirecek, bedeninizi rahatlatacak ve ruhunuzu besleyecektir.</p>
                    <blockquote>“Hayat, siz planlar yaparken başınızdan geçenlerdir.” - John Lennon</blockquote>
                    <p>Dinlemek, sadece kulaklarımızla değil, kalbimizle de duymaktır. İç sesimizi dinlemek, sezgilerimize güvenmek, bedenimizin bize gönderdiği sinyalleri fark etmek… Tüm bunlar, kendimizle daha derin bir bağ kurmamızı sağlar. Aynı zamanda, etrafımızdaki insanları gerçekten dinlemek, onların duygularını anlamaya çalışmak, empati kurmak da ilişkilerimizi güçlendirir.</p>
                    <p>Hissetmek, duygularımızı bastırmak yerine onları kabul etmek, onlarla yüzleşmek ve onları ifade etmektir. Korku, öfke, üzüntü gibi “olumsuz” olarak etiketlediğimiz duygular da hayatın bir parçasıdır. Onları reddetmek yerine, neden ortaya çıktıklarını anlamaya çalışmak, bize kendimiz hakkında önemli ipuçları verir.</p>
                    <p>Yavaşla, dinle, hisset… Bu üç kelime, hayatınıza daha fazla huzur, mutluluk ve anlam katacak sihirli bir formül gibidir. Unutmayın, hayat bir maraton değil, keyfini çıkarmanız gereken bir yolculuktur.</p>
                     <a href="#contact" class="button button-yellow">Deneyimlerini Paylaş</a>
                </article>

                <article class="diary-entry">
                    <span class="entry-date">05 Nisan 2024</span>
                    <h2><a href="#">İçindeki Çocukla Barışmak: Geçmişin İzlerini Şifalandırmak</a></h2>
                    <p>Hepimizin içinde, geçmişten gelen yaraları, kırgınlıkları ve özlemleriyle yaşayan bir çocuk var. Bazen onu unutur, bazen görmezden gelir, bazen de susturmaya çalışırız. Oysa içimizdeki çocukla barışmak, geçmişin izlerini şifalandırmak ve daha bütün bir “ben”e ulaşmak için atılacak en önemli adımlardan biridir.</p>
                    <p>İçimizdeki çocuk, saf, masum, meraklı ve sevgi doludur. Ama aynı zamanda, yaşadığı travmalar, hayal kırıklıkları ve ihmaller nedeniyle incinmiş, korkmuş ve güvensiz de olabilir. Yetişkinlik hayatımızda karşılaştığımız birçok sorunun kökeninde, aslında içimizdeki çocuğun karşılanmamış ihtiyaçları ve iyileşmemiş yaraları yatar.</p>
                    <p>Peki, içimizdeki çocukla nasıl barışabiliriz? İşte size birkaç öneri:</p>
                    <ul>
                        <li><strong>Onu Dinleyin:</strong> Sessiz bir anınızda, gözlerinizi kapatın ve çocukluğunuza gidin. O küçük çocuğu karşınızda hayal edin. Ona ne söylemek istersiniz? Onun size ne söylemek istediğini dinleyin. Belki de sadece anlaşılmaya, sevilmeye ve güvende hissetmeye ihtiyacı vardır.</li>
                        <li><strong>Ona Şefkat Gösterin:</strong> İçinizdeki çocuğa karşı yargılayıcı olmayın. Onun duygularını, korkularını ve hayal kırıklıklarını anlamaya çalışın. Ona sarılın, onu teselli edin ve ona ne kadar değerli olduğunu söyleyin.</li>
                        <li><strong>Onunla Oyun Oynayın:</strong> Yetişkinliğin getirdiği sorumluluklar arasında kaybolurken, içimizdeki çocuğun en sevdiği şeyi unuturuz: oyun oynamak! Kendinize zaman ayırın ve çocukken yapmaktan keyif aldığınız şeyleri yapın. Resim yapın, şarkı söyleyin, dans edin, doğada vakit geçirin… İçinizdeki çocuğun neşesini ve yaratıcılığını yeniden keşfedin.</li>
                        <li><strong>Geçmişi Affedin:</strong> Geçmişte yaşadığınız olumsuz deneyimler için kendinizi veya başkalarını suçlamak yerine, affetmeyi seçin. Affetmek, geçmişi değiştirmek anlamına gelmez, ama geçmişin üzerinizdeki etkisini azaltır. Affetmek, özgürleşmektir.</li>
                    </ul>
                    <p>İçimizdeki çocukla barışmak, bir süreçtir. Sabır, şefkat ve anlayış gerektirir. Ama bu yolculuğun sonunda, daha huzurlu, daha mutlu ve daha bütün bir “siz”e ulaşacaksınız. Unutmayın, içinizdeki çocuk sizin en değerli hazinenizdir. Ona iyi bakın.</p>
                     <a href="#contact" class="button button-yellow">Düşüncelerini Yaz</a>
                </article>
            </section>

            <!-- SHOP SECTION (Selling Writings) -->
            <section id="shop" class="content-section">
                <h1>Harlofias Dükkan</h1>
                <p style="text-align: center; margin-bottom: 40px;">İçsel yolculuğunuza rehberlik edecek, ruhunuza dokunacak dijital yazılar, e-kitaplar ve atölyeler.</p>

                <div class="shop-grid">
                    <div class="shop-item">
                        <div class="product-cover">"Kendi Hikayenin Kahramanı Ol" E-Kitap Kapağı</div>
                        <div>
                            <h3>"Kendi Hikayenin Kahramanı Ol" Rehber E-Kitap</h3>
                            <p>Hayatınızın direksiyonuna geçmek, içsel gücünüzü keşfetmek ve kendi değerlerinizle uyumlu bir yaşam inşa etmek için adım adım pratik bir rehber. İlham verici hikayeler ve dönüştürücü egzersizler içerir.</p>
                            <p class="price">₺220</p>
                        </div>
                        <a href="#" class="button button-pink">Hemen Satın Al</a>
                    </div>

                    <div class="shop-item">
                        <div class="product-cover">"An'da Kalma Sanatı" Online Atölye</div>
                        <div>
                            <h3>"An'da Kalma Sanatı" Online Atölye Kaydı</h3>
                            <p>Stresle başa çıkmak, zihinsel berraklık kazanmak ve günlük yaşamda farkındalığı artırmak için tasarlanmış interaktif online atölye. Meditasyon, nefes teknikleri ve pratik uygulamalar.</p>
                            <p class="price">₺550</p>
                        </div>
                        <a href="#" class="button button-blue">Atölyeye Kayıt Ol</a>
                    </div>

                    <div class="shop-item">
                        <div class="product-cover">"İçsel Çocukla Barışma" Yazı Dizisi</div>
                        <div>
                            <h3>"İçsel Çocukla Barışma" Premium Yazı Dizisi (PDF)</h3>
                            <p>Geçmişin izlerini şifalandırmak, öz-şefkati geliştirmek ve içsel çocuğunuzla derin bir bağ kurmak için rehber niteliğinde, özel olarak hazırlanmış 7 bölümlük yazı dizisi.</p>
                            <p class="price">₺150</p>
                        </div>
                        <a href="#" class="button button-yellow">İncele ve Al</a>
                    </div>
                     <div class="shop-item">
                        <div class="product-cover">"Harlofias Farkındalık Günlüğü" Şablonları</div>
                        <div>
                            <h3>"Harlofias Farkındalık Günlüğü" Dijital Şablon Paketi</h3>
                            <p>Günlük tutma alışkanlığınızı derinleştirmek, duygularınızı ve düşüncelerinizi keşfetmek için özel olarak tasarlanmış, estetik ve yönlendirici dijital günlük şablonları. (Yazdırılabilir PDF)</p>
                            <p class="price">₺95</p>
                        </div>
                        <a href="#" class="button button-pink">Şablonları Edin</a>
                    </div>
                </div>
            </section>

            <!-- ABOUT SECTION (Content from nisabilmez.com/hakkimda with IMAGE) -->
            <section id="about" class="content-section">
                <h1>Ben Nisa, Harlofias'ın Kalbi</h1>
                <div class="about-image-container">
                    <img src="nisa-profil.jpg" alt="Nisa Bilmez - Harlofias" class="profile-image">
                </div>
                <p>Merhaba, ben Nisa. Kelimelerin büyüsüne kapılmış, satır aralarında hayatın anlamını arayan, yazarak nefes alan biriyim. Çocukluğumdan beri içimde taşıdığım o bitmek bilmeyen merak duygusu, beni hep yeni keşiflere, farklı bakış açılarına ve en önemlisi de kendi iç dünyamın derinliklerine doğru bir yolculuğa çıkardı.</p>
                <p>İstanbul’un karmaşasında büyürken, sığındığım en güzel limanlardan biri kitaplar ve defterler oldu. Okudukça öğrendim, yazdıkça anladım. Anladım ki, hayat sadece dışarıda akıp giden bir nehir değil, aynı zamanda içimizde çağlayan bir deryaymış. Ve bu deryanın kıymetini bilmek, onunla barışık yaşamak, en büyük zenginlikmiş.</p>
                <p><strong>Harlofias</strong>, işte bu içsel yolculuğun, bu keşif arzusunun bir meyvesi. `nisabilmez.com`'da yıllardır sizlerle paylaştığım düşüncelerin, duyguların ve deneyimlerin daha sakin, daha derin ve daha estetik bir limanı. "Harmoni" ve "filozofi" kelimelerinin bir araya gelmesiyle oluşan bu isim, benim için içsel uyumu, yaşamın bilgeliğini arayışı ve bu arayışta kendimizle kurduğumuz o samimi bağı temsil ediyor.</p>
                <p>Burada, modern dünyanın gürültüsünden biraz olsun uzaklaşmak, yavaşlamak, kendi iç sesimize kulak vermek ve etrafımızdaki o küçük mucizeleri fark etmek için bir araya geliyoruz. Doğanın dinginliğinden, sanatın ilhamından ve spiritüel öğretilerin rehberliğinden güç alarak, kendi içsel bahçemizi yeşertmeye çalışıyoruz.</p>
                <p>Bu platformda okuyacağınız her bir yazı, katılacağınız her bir atölye veya edineceğiniz her bir dijital ürün, benim kendi deneyimlerimden, öğrendiklerimden ve kalbimden süzülerek sizlere ulaşıyor. Amacım, sizlere sadece bilgi aktarmak değil, aynı zamanda kendi içsel potansiyelinizi keşfetmeniz, kendi hikayenizin kahramanı olmanız ve yaşamınızı daha bilinçli, daha anlamlı ve daha huzurlu bir şekilde sürdürmeniz için ilham vermek.</p>
                <p>Unutmayın, her birimiz eşsiziz ve her birimizin anlatacak değerli bir hikayesi var. Harlofias, bu hikayeleri paylaşmak, birbirimizden öğrenmek ve birlikte büyümek için bir buluşma noktası.</p>
                <p>Bu huzurlu limanda bana eşlik ettiğiniz için kalpten teşekkür ederim. Yolumuz açık, kalbimiz ferah olsun.</p>
                <p>Sevgi ve ışıkla,</p>
                <p>Nisa Bilmez</p>
            </section>

            <!-- CONTACT SECTION -->
            <section id="contact" class="content-section">
                <h1>İletişime Geçin</h1>
                <p style="text-align: center;">Benimle bir fincan sıcak çay eşliğinde sohbet etmek, aklınızdaki soruları sormak, projelerinizden bahsetmek ya da sadece kalbinizden geçenleri paylaşmak isterseniz, aşağıdaki formu doldurabilir veya <a href="mailto:merhaba@harlofias.com">merhaba@harlofias.com</a> adresine e-posta gönderebilirsiniz. Her mesaja değer veriyor ve en kısa sürede geri dönmeye özen gösteriyorum.</p>

                <form action="#" method="POST" class="contact-form">
                    <div class="form-group">
                        <label for="name">Adınız Soyadınız:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">E-posta Adresiniz:</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="subject">Konu:</label>
                        <input type="text" id="subject" name="subject">
                    </div>
                    <div class="form-group">
                        <label for="message">Mesajınız:</label>
                        <textarea id="message" name="message" rows="6" required></textarea>
                    </div>
                    <div style="text-align: center;">
                        <button type="submit" class="button button-green" style="background-color: var(--heading-color); color: white;">Mesajımı Gönder</button>
                    </div>
                </form>
                <p style="text-align: center; margin-top: 30px;">Harlofias'ı sosyal medyada da takip ederek güncel paylaşımlardan haberdar olabilirsiniz (çok yakında!).</p>
            </section>
        </main>

        <footer>
            <p>© <span id="currentYear"></span> Harlofias by Nisa Bilmez. Tüm hakları saklıdır.</p>
            <p>Bir içsel keşif ve huzur güncesi.</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const navLinks = document.querySelectorAll('nav .nav-link, .logo a');
            const contentSections = document.querySelectorAll('.content-section');
            const defaultSection = 'diary';

            function updateActiveContent() {
                let targetId = window.location.hash.substring(1) || defaultSection;
                const validIds = Array.from(contentSections).map(s => s.id);
                if (!validIds.includes(targetId)) {
                    targetId = defaultSection;
                    if (history.pushState) {
                        history.pushState(null, null, '#' + targetId);
                    } else {
                        window.location.hash = targetId;
                    }
                }

                contentSections.forEach(section => {
                    section.classList.toggle('active', section.id === targetId);
                });

                navLinks.forEach(link => {
                    const linkTarget = link.getAttribute('href').substring(1);
                    link.classList.toggle('active', linkTarget === targetId);
                });
            }

            window.addEventListener('hashchange', updateActiveContent);
            updateActiveContent(); 

            document.getElementById('currentYear').textContent = new Date().getFullYear();
        });
    </script>
</body>
</html>
