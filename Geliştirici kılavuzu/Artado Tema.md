# Artado Teması Nasıl Geliştirilir

Bu kılavuz, [Artado Search](https://www.artadosearch.com) için özel bir tema oluşturma sürecinde size yol gösterecektir. İster CSS'de yeni olun ister deneyimli bir geliştirici olun, Artado için benzersiz bir görünüm tasarlamak için ihtiyacınız olan adımları ve ipuçlarını bulacaksınız.

## Başlarken

Artado Search için bir tema oluşturmak için öncelikle CSS ile çalışacaksınız. Temanızı oluştururken canlı olarak test etmek için [Stylus Editor](https://add0n.com/stylus.html)'ı kullanabilir ve değişiklikleri gerçek zamanlı olarak görebilirsiniz.

 ### Stylus Editor'ü Yükleme

1. **Stylus'u Yükleyin**: Öncelikle, [Chrome Web Mağazası](https://chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne) veya [Firefox Eklentileri](https://addons.mozilla.org/en-US/firefox/addon/styl-us/)'nden Stylus tarayıcı eklentisini yükleyin.
2. **Stylus Editor'e Erişim**:
- Tarayıcınızın araç çubuğundaki Stylus simgesine tıklayın.
- Stillerinize erişmek için **Yönet**'i seçin.
- Temanızı oluşturmaya başlamak için **Yeni Stil Yaz**'a basın.

### Temanızı Ayarlama

- **Hedef Artado Araması**: Stylus Editor'de, CSS'nizi yalnızca `https://www.artadosearch.com`'a uygulamak için "Şuna Uygulanır" ayarını değiştirin.  Bu, temanızın yalnızca Artado Arama'ya uygulanmasını ve ziyaret ettiğiniz her web sitesine uygulanmamasını sağlar.

## Temeller

### Arka Plan Resmi Ekleme

Arka planı özelleştirmek, temanızın tonunu ayarlamanın harika bir yoludur.

#### Ana Sayfa Arka Planı

Yalnızca ana arama sayfasında görünen bir arka plan resmi eklemek için:

```css
#homepage {
background: url("Resim bağlantısı") no-repeat center fixed;
-webkit-background-size: cover;
-moz-background-size: cover;
-o-background-size: cover;
background-size: cover;
}
```

#### Genel Arka Plan

Arka plan resmini arama sonuçları ve ayarlar dahil tüm sayfalara uygulamak için:

```css
body {
background-image: url("Resim bağlantısı");
}
```

### Arama Çubuğunu Özelleştirme

Arama çubuğu, sayfadaki en belirgin öğelerden biridir.  İşte özelleştirme yöntemi:

#### Arama Çubuğu Konteyneri

```css
#searchbar {
margin-bottom: 200px;
width: 550px !important; /* Otomatik Tamamlama Listesinin genişliğiyle eşleştiğinden emin olun */
border-radius: 10px; /* Düzgün köşeler */
}
```

#### Arama Giriş Bölümü

```css
#searchinput {
background-color: rgb(0, 0, 0); /* Giriş alanı arka plan rengi */
color: rgb(255, 255, 255); /* Metin rengi */
}
```

#### Arama Düğmesi

```css
#searchbutton {
color: rgb(255, 255, 255); /* Büyüteç simgesinin rengi */
background-color: rgb(0, 0, 0);  /* Düğme arka plan rengi */
}
```

### Alt Çubuğu Özelleştirme

Alt çubuk, genel temayı tamamlayacak şekilde biçimlendirilebilir:

```css
#features .flex-wrap {
padding-bottom: 20px; /* Dolguyu istediğiniz gibi ayarlayın */
padding-top: 20px;
color: #fff; /* Metin rengi */
background-color: #000; /* Arka plan rengi */
}
```

### Gelişmiş Özelleştirmeler

#### Hover Efektleri

Etkileşimli öğeler için hover efektleri eklemek için:

```css
#searchbutton:hover {
background-color: rgb(255, 165, 0); /* Hover'da düğme rengini değiştir */
color: #000;  /* Üzerine gelindiğinde metin/simge rengini değiştir */
}
```

#### Tipografi

Yazı tipini ve metin stillerini özelleştirmek için:

```css
body {
font-family: 'Arial', sans-serif;
font-size: 16px;
color: #333; /* Temel metin rengi */
}

h1, h2, h3 {
font-family: 'Georgia', serif;
color: #444;
 }
```

### Örnek Temalar

İlham ve öğrenme için Artado topluluğu tarafından oluşturulan bu örnek temaları keşfedin:

- [Merkür Teması](https://github.com/KerimCan05/merkur-artadotheme/)
- [Atatürk Teması](https://github.com/KerimCan05/ataturk-artadorheme/)
- [HereUS UI 3.1](https://github.com/islekcaganmert/artado-hereus-ui-3.1-theme)

### Test ve Hata Ayıklama

Temanız üzerinde çalışırken, öğeleri incelemek, CSS değişikliklerini test etmek ve sorunları gidermek için tarayıcı geliştirici araçlarını (`F12` veya `Ctrl+Shift+I`) kullanın.

## Daha Fazla Bilgi Edinin

Bu sadece başlangıç.  Daha sofistike temalar oluşturmakla ilgileniyorsanız, CSS dünyasına daha derinlemesine dalın:

- [CSS Temelleri](https://www.w3schools.com/css/css_intro.asp) - CSS'ye yeni başladıysanız harika bir başlangıç noktası.
- [CSS Püf Noktaları](https://css-tricks.com/) - Stillerinizi geliştirmek için gelişmiş teknikler ve ipuçları.
- [MDN Web Belgeleri](https://developer.mozilla.org/en-US/docs/Web/CSS) - CSS özellikleri ve en iyi uygulamalar için kapsamlı kaynak.

## Temalarınızı Yükleyin

Temanızı oluşturduktan sonra, toplulukla paylaşın! Temanızı [Artado Devs](https://devs.artado.xyz/) adresine yükleyebilirsiniz:

1. **Hesap Oluşturun**: Artado Devs'e kaydolun veya giriş yapın.  2. **Temanızı Yükleyin**: Yükleme bölümüne gidin, bir açıklama girin ve yaratımınızı dünyayla paylaşın.

---

Bu kılavuz, Artado Search için özel temalar oluşturmanız ve paylaşmanız için size sağlam bir temel sağlamalıdır. Farklı stilleri deneyerek ve Artado Search'ü kendinize ait hale getirerek eğlenin!
