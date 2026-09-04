# Scroll Craft

Gelistirici: Halil Tek (@haliltek)
Mimari: Kaydirma Odakli (Scroll-Driven) Sinematik ve Editoryal Arayuz Muhendisligi

Standart yapay zeka ciktilari ve kaliplasmis sablon kutuphaneleri iki temel cikmaza saplanir: Ya birbirinin kopyasi, estetik derinligi olmayan kutu kutu 12 kolonluk izgaralar uretirler; ya da mobil performansi cokerten, tipografik hiyerarsiyi ezen ve okunurluktan uzak kontrolsuz animasyon yiginlari sunarlar.

Scroll Craft, bu yuzeysel tasarim reflekslerini tamamen reddeder. Arayuz gelistirmeyi yalnizca kod yazmak degil; negatif alan kontrolu, mikroskopik tipografi disiplini, ritmik bosluk muhendisligi ve tavizsiz bir etkilesim mimarisi olarak ele alir.

Bu depoda yer alan sistem, kaydirma (scroll) eylemini pasif bir sayfa kaydirma araci olarak degil, dogrudan sahnenin zaman cizelgesi (timeline) olarak isleyen ozel bir frontend calisma ortamidir.

---

## Temel Felsefe ve Muhendislik Yaklasimi

### 1. Kaydirma bir Zaman Cizelgesidir
Kullanicinin fare tekerlegi veya dokunmatik hareketi, sayfadaki video ve animasyon katmanlarini kare kare (frame-by-frame scrubbing) tarar. Bolumler belirli bir arguman tamamlanana kadar ekrana sabitlenir (pinning), raylar yatayda kontrollu kayar, tipografik bloklar mikrosaniyeler icinde hedeflenen ritimle acilir.

### 2. Sablonculuga Karsi Sekiz Mimari Gramer
Birbirini sessizce taklit eden sayfalar uretilmesini engellemek adina, her proje asagidaki sekiz kesin ve birbirini dislayan sayfa gramerinden biri uzerine kurulur. Bir gramerin zorunlu kildigi yapisal kural digerinde kesinlikle yasaktir:

- Sinematik Tek Cekim (Filmic One-Shot): Kesintisiz video akisi uzerine oturan, kare kare taranan tek bir sahne omurgasi.
- Bolumlu Editoryal (Chaptered Editorial): Baski disiplinine dayali baslik-yazi alanlari, sert kesimli zemin gecisleri ve editoryal agirlik.
- Canli Urun Yuzeyi (Live Surface): Tipografik gosteris yerine dogrudan urun arayuzunun, konsolun veya operasyon ekraninin baslangic sahnesi olmasi.
- Surekli Sahne / Dunya (Continuous World): Sayfada hicbir ayrik bolum blogu olmaksizin, sabit tek bir sahne icinde derinlik ekseninde suzulen ucus modu.
- Tipografik Poster (Typographic Poster): Medya iceriklerinin kaldirildigi, harf formlarinin ve ekstrem olcekli tipografinin bizzat gorsel haline geldigi yapi.
- Monografik Katalog (Gallery / Catalog): Muzecilik ciddiyetinde etiketleme, yalnizca gercek veriler, sifir pazarlama jargonu ve kontrollu ornek incelemeleri.
- Bolunmus Cift Fazli Sahne (Split Stage): Tek bir sahnede dikey veya yatay kesimle iki ayri durumun karsilastirildigi, kesim cizgisinin bizzat etkilesim araci oldugu yapilar.
- Ritmik Kesim Listesi (Rhythmic Cutlist): Sabitlenmis bolum kullanilmayan, yuksek tempolu ve net kesimlerle ilerleyen tipografik levhalar.

### 3. Parmak Izi ve Benzersizlik Kurali (Fingerprint Gate)
Urettigim her sayfa, onceki calismalarimdan en az dort temel boyutta (sayfa grameri, navigasyon modeli, hero mekanizmasi, bolum akis formu, kapanis deseni, imza hareketi) radikal bicimde farkli olmak zorundadir. Ayni kalibin farkli renklerle yeniden sunulmasi kabul edilmez.

### 4. Zorunlu Imza Hareketi (Signature Move)
Her arayuz, baska hicbir projede yer almayan ve bizzat o deneyime ozgu olan bir mikro etkilesim barindirmak zorundadir (orn. ivmeye duyarli fiziksel harf mekanikleri, imlece bagli isi haritalari, zaman kodlu log akislari vb.).

---

## Halil Tek Arayuz ve Zanaat Standartlari

- Tipografi Taban Kurali: Tek bir projede en fazla iki yazi tipi ailesi kullanilir. Baslik olcegi buyudukce harf araligi (tracking) kontrollu bicimde daraltilir. Metin genisligi 45 ila 75 karakter arasinda kilitlenir. Koyu zemin uzerindeki acik renk tipografi optik olarak kompanse edilir.
- Ritmik Bosluk Hiyerarsisi: 4px taban alinarak turlenen matematiksel ritim uygulanir. Bir basligin ustu, altindaki metinden her zaman belirgin sekilde daha genis bosluga sahiptir.
- Renk Disiplini: Alti temel rol ve yalnizca tek bir vurgu rengi kullanilir. Asla saf siyah (#000000) kullanilmaz. Duz griler yerine arkaplanin tonuyla beslenen sicak veya soguk ara tonlar tercih edilir.
- Bes Katmanli Derinlik: Arayuz tekduze duz golgeler yerine ofsetli golgeler, kenar isiklari, olcek-bulaniklik iliskisi, katman cakismalari ve mikroskobik gren dokulariyla hacimlendirilir.
- Sifir Ikon Prensibi: Icerik ucuz emoji ve ikon kalabaligiyla bogulmaz. Anlatim gucu saf tipografi, ritmik yerlesim, hiyerarsik agirliklar ve negatif alan ile saglanir.
- Yasaklar Listesi: Jenerik ozellik kartlari, birbirinin ayni 01/06 sayaclari, asagi kaydir ok veya cizgileri, yapay zeka moru degradeler, uydurma istatistik grafikleri kesinlikle kullanilmaz.

---

## Kendi Kendini Denetleyen Test Mekanizmasi

Gelistirilen sayfalar yayina alinmadan once Playwright tabanli basliksiz (headless) Chrome uzerinden otomatik denetime tabi tutulur:

- Olu Kaydirma Denetimi (Dead Scroll): Ekranda hicbir pikseli veya durumu degistirmeyen bos kaydirma hareketlerini tespit eder.
- Okunaksiz Metin Analizi: Opakligi hicbir zaman tam netlige ulasmayan ve kullanicinin gozunu yoran elemanlari yakalar.
- Dinamik WCAG Kontrast Olcumu: Hareketli video veya arka plan gecisleri sirasinda her satirin altindan gecen en parlak karedeki kontrast oranini piksel duzeyinde denetler.
- Donmus Kare Kontrolu: Cozumlenememis veya takilmis video durumlarini raporlar.

---

## Proje Mimarisi

```
scroll-craft/
├── plugins/
│   └── scroll-craft/
│       └── skills/
│           └── scroll-craft/
│               ├── SKILL.md          Tasarim, gramer ve insa prosedurleri
│               ├── engine/           scrollcraft.js ve scrollcraft.css (cekirdek motor)
│               ├── references/       Mimari referanslar, tipografi ve cihaz kurallari
│               └── scripts/          Otomasyon, donusum ve dogrulama betikleri
├── EXAMPLES.md                       Uretilen projelerin parmak izi kayit tablosu
├── README.md                         Genel mimari tanitim ve manifestosu
└── LICENSE                           MIT Lisansi
```

Cekirdek motor (`engine/`) saf etkilesim mekanizmasidir ve proje bazinda manuel olarak kirletilmez. Tum ozel tasarim ve tipografik detaylar projenin semantik HTML yapisi ve motorun sundugu `--sc-p` ozel CSS degiskeni uzerinden bicimlendirilir.

---

## Calisma Ortami ve Betikler

On hazirlik ve calisma alani yapilandirmasi icin terminalden su adimlar izlenir:

```bash
# Sistem bagimliliklarini ve FFmpeg surumunu denetler
node plugins/scroll-craft/skills/scroll-craft/scripts/doctor.mjs

# Calisma alanini ve parmak izi kutugunu hazirlar
node plugins/scroll-craft/skills/scroll-craft/scripts/workspace.mjs --ensure
```

Gereksinimler:
- Node.js 18 ve uzeri
- Kare kare kaydirma donusumleri icin tam paket FFmpeg
- Otomatik dogrulama testleri icin Playwright Core ve Chrome

---

## Lisans

Bu proje MIT lisansi ile korunmaktadir. Ayrintilar icin `LICENSE` dosyasina bakabilirsiniz.
