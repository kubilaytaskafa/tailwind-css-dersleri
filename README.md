# -DERS 1 TAİLWİND CSS NEDİR?-

#### Tailwind css html tarafından ayrılamadan tasarım yapmamızı sağlar.

#### bootstrapten farklı olarak component olarak vermez.

#### yazdığımız tailwind kodları arka planda css olarak çalışır.

#### Tailwind CSS IntelliSense extension u sayesinde tailwind yazarken crtl+space yaptığınızda size ilgili tailwind kodlarını gösterir.

#### tailwind sayesinde responsive tasarım yapmak oldukça kolaydır.

# DERS-2 TAİLWİND UI,TAİLWİND COMPONENTS,TEMPLATES

#### tailwind web sayfası :https://tailwindcss.com/

#### sayfanın en üst sağ kısmından "Components" bölümüne geldiğimizde bizleri tailwindUI bölümüne alır.

#### tailwindUI bizlere tailwind tarafından hazırlanmış hazır componentleri gösterir.

#### tailwindUI içerisinde hazır template ve componentler vardır. fakat ücretlidir.

#### !!tavsiye!!!

#### Tailwind CSS IntelliSense extension u sayesinde tailwind yazarken crtl+space yaptığınızda size ilgili tailwind kodlarını gösterir.

#### Auto Rename Tag extensionunu da kullanabilirsiniz.

<<<<<<< HEAD

# DERS 3 TAİLWİND CSS KURULUMU

#### tailwindin kendi sitesinde kurulum ile ilgili rehber vardır.

#### tailwind installation kısmına girerseniz çeşitli kurulum yollarını görebilirsiniz.

#### tailwind css frameworkler ile çalışabilir ve istediğiniz framework'e tailwind css nasıl kurulur installation bölümündeki framework guides kısmından ulaşabilirsiniz.

## TAİLWİND CSS PLAY CDN İLE KURULUMU

#### eğer saf html üzerinde tailwind.css kullanmak istiyorsak html sayfamıza tailwind.css dosyamızı import ederek kullanabiliriz.

#### örnek:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- tailwind.css dosyamız. -->
    <script src="https://cdn.tailwindcss.com"></script>
  </head>
  <body>
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
  </body>
</html>
```

#### eğer tailwind config dosyasında değişiklik yapmak istiyorsanız bu dosyayı da script ile oluşturabilirsiniz.

#### örnek:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <!-- tailwind.css dosyamız. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- tailwind.config dosyamız. -->
    <script>
      tailwind.config = {
        theme: {
          extend: {
            colors: {
              // tailwindde olmayan bir rengi özel olarak eklemişiz bu konu ileride anlatılacaktır.
              clifford: "#da373d",
            },
          },
        },
      };
    </script>
  </head>
  <body>
    <h1 class="text-3xl font-bold underline **text-clifford**">Hello world!</h1>
  </body>
</html>
```

#### extra olarak kendi css komutlarınızı eklemek istiyorsanız style tagı içerisinde type özelliğini vererek kullanabilirsiniz.

#### bu özellikte kendi css düzenlemelerimizi tailwind ile beraber kullanabiliriz.

#### örnek:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- kendi css komutumuz -->
    <style type="text/tailwindcss">
      @layer utilities {
        .content-auto {
          content-visibility: auto;
        }
      }
    </style>
  </head>
  <body>
    <!-- screen lg olduğunda kendi css komutumuz çalışacaktır. -->
    <div class="lg:content-auto">
      <!-- ... -->
    </div>
  </body>
</html>
```

## -TAİLWİND CSS CLI İLE KURULUMU

#### öncelikle bilgisayarımızda nodejs kurulu olması gereklidir.

#### daha sonra node -v yazarak node sürümü ve kendisini test ederiz.

#### daha sonra vscode üzerinde terminali açarız

#### !terminali açmak için ctrl+é tuşuna basabiliriz.

#### terminali açtıktan sonra :

```
npm init
```

#### komutunu çalıştırırız.

#### bu komut bizlere dosyamız içerisinde bir package.json dosyası oluşturur.

#### daha sonra terminalden proje dosyamıza tailwind.css i indiririz.

#### tailwind.css indirme komutu

```
npm install -D tailwindcss
```

#### bu işlemden sonra ise tailwind.config dosyamızı projemize ekleriz.

#### tailwind.config dosyası indirme komutu

```
npx tailwindcss init
```

#### tüm bu işlemlerden sonra sıra tailwind.config dosyamızı güncellemekte

#### tailwind.config içerisinde content kısmını güncelliyoruz.

#### content kısmını neden güncelleriz? Çünkü content kısmına hangi dosya isimlerini verirsek tailwind o dosyalar üzerinde çalışabilecek

#### tailwind.config dosyası güncelleme

```
<!-- eski config dosyası -->
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [],
  theme: {
    extend: {},
  },
  plugins: [],
}

  <!-- yeni config dosyası -->
  /** @type {import('tailwindcss').Config} */
module.exports = {
    <!-- config dosyası güncellendi -->
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],

}

```

#### sonraki adımda projemize 2 tanek lasör ekliyoruz. src ve dist

#### src klasörümüz içerisinde girip bir ana css dosyası oluşturuyoruz.

#### ana css içerisine de tailwindi çalıştırmak için gerekli olan komutları ekliyoruz:

#### ana css dosyasına istediğimiz ismi verebiliriz.

```main.css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### src içerisinde bir index.html dosyası açtık ve bu dosya içerisinde tailwind kullanmak istiyorsak son olarak terminalde bir komut çalıştıracağız.

```Terminal
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch
<!-- burada input.css yerine tailwind komutlarını eklediğimiz ana css dosyamızın ismini vereceğiz. -->
```

#### bu komut ile tailwind ana css içerisindeki değişiklikleri output olarak css dosyasına çıkarıp izleyecektir.

#### bu watch işlemini sürekli terminalde çalıştırmanın kolay bir yolu daha var.

#### package.json dosyasında scripts kısmına giderek istediğimiz key ile watch komutunu eklersek. verilen key i npm run key diyerek çalıştırabiliriz.

#### örnek:

```package.json
"dev":"npx tailwindcss -i ./src/input.css -o ./src/output.css --watch"
```

#### artık her dev komutu çalıştığında watch işlemi çalışacak

### !!!! TEBRİKLER ARTIK TAİLWİND YAZABİLİRSİNİZ !!!!!!!!

# -DERS-4 TAİLWİND CSS APPLY ,LAYER BASE VE COMPONENT KULLANIMI-

#### bazen sitelerde çok fazla aynı componenti kullanıyor olabiliriz.

#### geliştirme sürecinde sürekli olarak copy paste yapmak bizi yorabilir.

#### daha kötüsü diyelim bir buton tanımlaması yapıp 30 yerde kullandık fakat butonun renginin değişmesi gerekti.30 farklı componentte bu değişikliği yönetmek oldukça zordur.

#### tailwind bizlere bu konuda yardımcı oluyor. Tailwind sayesinde belirli style işlemlerini bir classa bağlayarak kullanabiliriz.

```
<!-- kendi classlarımızı @layer components içerisinde yazacağız. -->
@layer components{
  <!-- kendi classımız bu classı artık isteidğimiz yerde kullanabiliriz. -->
  .btn-primary{
    <!-- @apply ile tailwind css kodlarımızı tutarız. -->
    @apply py-2 bg-red-400
  }
}
```

### -Layer Base kullanımı-

#### base ile standart etiketlere müdahale etmemizi sağlar.

#### layer base kullanarak html etiketlerine kendi özelliklerimizi atarız.

#### base kullanarak kendi classımızı değil de kendi etiketimizi oluşturuyoruz.

#### kullanımı:

```
@layer base{
  <!-- kendi h1 etiketimizi tanımladık artık kullandığımız bütün h1 ler kırmızı renginde ve 3xl boyutunda olacaktır. -->
  h1{
    @apply text-red-400 text-3xl
  }
}
```

#### @apply tanımlamasını kullanmazsanız verdiğiniz style özellikleri çalışmaz.

#### örnek:

```
@layer base{
  p{
    <!-- bütün p etiketlerimiz kalın yazılacaktır. -->
    @apply font-bold
  }
}
```

# -DERS-5 TAİLWİND CSS BREAKPOİNTS RESPONSİVE DESİGN-

#### tailwind ile responsive design yapmak kolaydır.

#### tailwind classları içerisinde breakpointsler mevcuttur.

### breakpoint nedir?

#### breakpoint, tarayıcı sayfasının belirli px lere göre adlandırılmasıdır.

#### aşağıda tailwindin breakpoint lerini görüyorsunuz .

```
Breakpoint prefix	Minimum width	CSS
sm	640px	@media (min-width: 640px) { ... }
md	768px	@media (min-width: 768px) { ... }
lg	1024px	@media (min-width: 1024px) { ... }
xl	1280px	@media (min-width: 1280px) { ... }
2xl	1536px	@media (min-width: 1536px) { ... }
```

#### bir elementin classında bu breakpointleri kullanarak tasarım yapabilirsiniz ve responsive tasarımlarınızı kolayca oluşturabilirsiniz.

#### örnek:

```html
<!-- img etiketi  width değeri default olarak 16 (16 px değil tailwind kendi içnde değerlendirme yapar.) -->
<!--img etiketi medium breakpointte yani min width 768px olduğunda 32   -->
<!-- img etiketi lg breakpointte yani min width 1024px olduğunda 48 dir. -->
<img class="w-16 md:w-32 lg:w-48" src="..." />
```

#### mobile bir cihazda tasarım yaparken sm değerini kullanmanıza gerek yoktur.

#### yukarıdaki örnekte gördüğünüz üzere sm değeri kullanmadık. aslında sm değeri başta verdiğimiz w-16 değeridir.

### örnek

```html
<!-- burada işlediğimiz classlara göre elementimizin rengi değişecektir. -->
<p class="text-red-600 md:text-red-800 lg:text-red-500">HEllo</p>
```

# - DERS-6 TAİLWİND CONTAİNER-

#### tailwind de container classımız vardır.

#### container classımız sayesinde elementimizin yükseklik ve genişliğini ayarlayabiliriz. container ı kullandığımız zaman tarayıcının boyutuna göre bizlere width değeri ekler.

#### tabii ki container ile birlikte birden çok hizalama classımız mevcuttur .

### mx-auto classı :

#### bir elementte eğer mx-auto classını kullanırsanız tailwind o elementi sağdan ve soldan ortalar .

#### örnek:

```html
<!-- burada container classı ile birlikte mx-auto kullandık ve divimiz sağdan soldan ortalandı. -->
<div class="container mx-auto"></div>
```

#### dikkat ! container classı ile hizalama classını kapsayıcı divde kullanmak mantıklıdır. eğer kapsayıcı divde kullanmazsak sayfaya eklenen her elementte container ile hizalama classlarını kullanırız. bu da clean code açısından bizleri patlatır.

#### unutmayın en iyi yazılımcı az ve öz kod yazan yazılımcıdır. BİZLER KATİP DEĞİLİZ!!!

#### örnek

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div class="container mx-auto">
      <div class="bg-gray-600">
        <h1>1. div</h1>
      </div>
      <div class="bg-red-600">
        <h1>2.div</h1>
      </div>
    </div>
  </body>
</html>
<!-- burada gördüğünüz üzere ana kapsayıcı dive container mx-auto dedik bu sayede kapsayıcı içinde bulunan her bir div tarayıcıda ortalanır. -->
```

# -DERS 7 TAİLWİND BOX SİZİNG-

#### bizler bir web sitesi geliştirirken html kullanırız. Html de ise yüksek oranda divler kullanarak birleştirme işlemi yaparız.

#### html de div ler box(kutu) dur.

#### işte kullandığımız bu divlerin witdh height değerleri, taşma durumları bizim için önemlidir. Çünkü divin içine eklediğimiz eleman divden taşabilir.

#### bizler css de box sizing özelliği ile özelliği ile divlerimizin width,height ve taşma özelliklerini yönetebiliriz.

#### Tailwind'de box sizing özelliği 2 şekilde tanımlanmıştır:

- BOX-BORDER

#### box-border özelliğinde bir elementin padding ve border özelliği kutunun genişlik yüksekliğine dahil edilir.

#### yani sizler border-box olan bir dive 200px genişlik verdiğinizde içerisindeki element paddin ve border dahil 200px olur.

#### örnek:

```html
<!-- burada divimizin box özelliği border   -->
<!-- yani div içindeki padding ve border dahil olmak suretiyle  w-64 değerini alır.  -->
<div class="box-border w-64">kutu!</div>
```

- BOX-CONTENT

#### box-content özelliği box-border özelliğine nazaran sadece içeriği hedef alır .

#### yani box-content özelliği alan bir dive verdiğiniz width ve height değerleri border ve paddingi dahil etmeden eklenir.

#### örnek:

```html
<!-- burada divimizin box özelliği content -->
<!-- yani divimizin witdh değeri margin padding eklenmeden w-64 tür. -->
<div class="box-content w-64">kutu'</div>
```

### Peki aralarındaki fark nedir?

#### sizler 2 tane dive de aynı width değerleri verip box özelliklerini farklı yazdığınızda:

#### box özelliği content olanın genişliği daha fazla olacaktır.

# DERS-8 TAİLWİND DİSPLAY-

#### display elementin bir web sitesi üzerinde nasıl gözükmesi gerektiğini belirlediğimiz tanımlamadır.

#### örneğin displayi block olan element aynı satırda yanına başka bir element alamaz çünkü bulunduğu satırı tamamen kaplar.

#### bizler display durumlarını değiştirerek tasarımlarımızda kişisel tercihler yapabiliriz.

#### Tailwindde bizler display özelliğini çeşitli classlarla kullanırız.

#### tailwindde display özelliği vermek için sadece class içerisinde vermek istediğiniz display özelliğini yazmak yeterlidir.

```
          TAİLWİND-DİSPLAY-ÖZELLİKLERİ-

 Class     Properties
block	   display: block;
inline-block   	display: inline-block;
inline   	display: inline;
flex	   display: flex;
inline-flex	   display: inline-flex;
table	   display: table;
inline-table	   display: inline-table;
table-caption	   display: table-caption;
table-cell	   display: table-cell;
table-column	   display: table-column;
table-column-group	   display: table-column-group;
table-footer-group	   display: table-footer-group;
table-header-group	   display: table-header-group;
table-row-group	display:    table-row-group;
table-row   	display: table-row;
flow-root	   display: flow-root;
grid	   display: grid;
inline-grid   	display: inline-grid;
contents   	display: contents;
list-item	   display: list-item;
hidden	   display: none;
```

# DERS-9 TAİLWİND HOVER,FOCUS VB,-

#### CSS deki hover, focus gibi uygulamalarımızı tailwindde yapmak daha basittir.

### Hover :

#### tailwindde hover efekti vermek için class olarak hover: kullanmak yeterlidir.

#### örnek:

```html
<!-- Burada div e hover durumu olduğunda divin arkaplan rengi siyah olacaktır.   -->
<div class="bg-red-600  hover:bg-black">Kutu 1</div>
```

#### !! dikkat hover durumunda vereceğiniz her bir özelliği tek tek hover: kullanarak vermelisiniz.

#### örnek:

```html
<!-- burada 2 ayrı hover durumu ekledik. bu eklemeyi yaparken 2 tane hover kullandık. -->
<div class="bg-red-600 text-white hover:bg-black hover:text-red-500"></div>
```
