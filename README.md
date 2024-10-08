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
