# Artado Uzantısı Nasıl Geliştirilir

Bu kılavuz, [Artado Search](https://www.artadosearch.com) için uzantılar oluşturmanıza yardımcı olacaktır. Uzantılar, özel işlevler eklemenize, kullanıcı deneyimini geliştirmenize veya üçüncü taraf hizmetlerini doğrudan Artado Search'e entegre etmenize olanak tanır.

## Başlarken

Artado Search için bir uzantı geliştirmek için HTML, CSS ve JavaScript hakkında temel bir anlayışa sahip olmanız gerekir.
JavaScript, tarayıcıda çalışan ve web sayfalarının içeriğini değiştirmenize, API'lerle etkileşime girmenize ve daha fazlasına olanak tanıyan güçlü bir dildir.
Javascript'in temelleri hakkında bilgi edinmek için bu belgelere göz atabilirsiniz.

### İhtiyaç Duyacağınız Araçlar

- **Metin Düzenleyici veya IDE (İsteğe Bağlı)**: [Visual Studio Code](https://code.visualstudio.com/), [Sublime Text](https://www.sublimetext.com/) veya [Atom](https://atom.io/) gibi herhangi bir kod düzenleyicisini kullanın.  - **Web Tarayıcısı**: Uzantınızı test etmek ve hata ayıklamak için.

## Temeller

### İlk Uzantınızı Oluşturma

1. **Yeni Bir JavaScript Dosyası Oluşturma**:
- Metin düzenleyicinizde yeni bir `.js` dosyası oluşturarak başlayın.
- Bu dosya, uzantınızın mantığını içerecektir.

2. **Temel Yapı**:
- Başlamanız için basit bir şablon:
```javascript
if (window.location.pathname === "/search") { // Kullanıcı 
const urlParams = new URLSearchParams(window.location.search);
 const search = urlParams.get('i').replace("+", " ").trim()
.replace(/[!"#\$%&'\(\)\*\+,-\.\/:;<=>\?@\[\\\]\^_`{\|}~]/g, "").replace(/ +/g, " "); // Aranan sorguyu alır

const searches = [
"ip'im nedir",
"ip'im nedir",
"ip'im nedir",
"ip'im",
];

if (searches.includes(search)) { // Sorgunun IP ile ilgili olup olmadığını kontrol eder
fetch('https://api.ipify.org?format=json')
.then(response => response.json())
.then(data => {
var element = document.createElement("div"); // Oluşturur  arama sayfasındaki bir öğe
element.className = "card";
element.style = "border: 1px solid #bdbdbd; text-transform: none";
element.innerHTML = `<p>IP adresiniz: <code>${data.ip</code></p>`;

document.getElementById("web_results").insertBefore(element, document.getElementById("web_results").firstChild);
});
}
}
```

3. **Uzantıyı Yükle**:
- Uzantıyı test etmek için Artado Search'e yükleyin. Bunu kodunuzu tarayıcının konsoluna yapıştırarak veya komut dosyanızı Artado Search'e enjekte eden bir tarayıcı uzantısı oluşturarak manuel olarak yapabilirsiniz.

4. **Test**:
- Tarayıcınızda Artado Search'ü açın.  - Sayfayı incelemek, uzantınızı çalıştırmak ve sorunları ayıklamak için tarayıcının geliştirici araçlarını (`F12` veya `Ctrl+Shift+I`) kullanın.

### Kullanıcı Arayüzünü Değiştirme

Artado Arama arayüzünü özel HTML ekleyerek veya mevcut öğeleri değiştirerek de değiştirebilirsiniz:

```javascript
(function() {
// Arama çubuğuna özel bir düğme ekleyin
let button = document.createElement("button");
button.innerText = "Özel Eylem";
button.onclick = function() {
alert("Düğmeye tıklandı!");
};
document.querySelector("#searchbar").appendChild(button);
})();
```

3. **Uzantınızı Yükleyin**: Uzantıyı [Artado Devs](https://devs.artado.xyz/) adresine yükleyerek Artado topluluğuyla paylaşabilirsiniz.

 ## Örnek Uzantılar

Artado topluluğu tarafından geliştirilen birkaç örnek uzantı şunlardır:

- [**SecimCountdown**](https://www.artadosearch.com/Workshop/55): 2024'te Türkiye'de yapılacak yerel seçimler için geri sayım.
- [**Sözlük Widget'ı**](https://www.artadosearch.com/Workshop/64): Artado Arama için bir sözlük widget uzantısı
- [**IP adresim nedir**](https://www.artadosearch.com/Workshop/65): "IP adresim nedir" widget'ı "IP adresim nedir" gibi aramalar için

## Daha Fazla Bilgi Edinin

Daha gelişmiş uzantılar oluşturmak için JavaScript ve web API'leri hakkındaki anlayışınızı derinleştirmeniz gerekir:

- [JavaScript Temelleri](https://www.w3schools.com/js/default.asp) - JavaScript'in temellerini öğrenin.
- [JavaScript.info](https://javascript.info/) - Ayrıntılı  öğreticiler ve kılavuzlar.
- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Kapsamlı JavaScript referansı.

## Uzantılarınızı Yükleyin

Uzantılarınız hazır olduğunda, [Artado Devs](https://devs.artado.xyz/) adresinde dünyayla paylaşın:

1. **Bir Hesap Oluşturun**: Artado Devs'e kaydolun veya oturum açın.
2. **Uzantılarınızı Yükleyin**: Bir açıklama sağlayın, dosyalarınızı yükleyin ve çalışmanızı Artado topluluğuyla paylaşın.

---

Bu kılavuz, Artado Search için uzantılar geliştirmeye ve paylaşmaya başlamanız için ihtiyacınız olan her şeyi sağlamalıdır. Artado deneyimini oluşturmanın ve geliştirmenin tadını çıkarın!
