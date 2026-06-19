# CVE Portfolyosu ve Güvenlik Araştırmaları

Güvenlik araştırmalarım ve zafiyet ifşalarımı içeren portfolyoma hoş geldiniz. Bu depo, çeşitli ürünlerde ve platformlarda keşfettiğim, doğrulanmış Ortak Zafiyetler ve Açıklar (CVE) kayıtlarını barındırmaktadır.

- ##Yayınlanmış CVE Kayıtları

| CVE ID | Üretici / Ürün | Zafiyet Türü | CVSS Skoru | Seviye | Resmi Kaynak |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **CVE-2025-5997** | Beamsec PhishPro | Ayrıcalıklı API'lerin Yanlış Kullanımı | 8.8 | ![High](https://img.shields.io/badge/-High-orange) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2025-5997) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2025-5997) |
| **CVE-2024-5619** | PruvaSoft Informatics Apinizer Management Console | Kullanıcı Kontrollü Anahtar Üzerinden Yetkilendirme Atlatma | 9.6 | ![Critical](https://img.shields.io/badge/-Critical-red) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2024-5619) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2024-5619) |
| **CVE-2024-5620** | PruvaSoft Informatics Apinizer Management Console | Kimlik Doğrulama Atlatma | 6.5 | ![Medium](https://img.shields.io/badge/-Medium-yellow) | [NVD Link](https://nvd.nist.gov/vuln/detail/CVE-2024-5620) / [CVE.ORG](https://www.cve.org/CVERecord?id=CVE-2024-5620)|

- ##Zafiyet Detayları ve Teknik Özetler

### [CVE-2025-5997] Beamsec PhishPro - Hak Yükseltme ve Bilgi İfşası
**Genel Bakış:** Uygulamanın kullanıcı yönetimi işlevlerinde veya API uç noktalarında kritik bir erişim kontrolü hatası tespit edilmiştir. 

**Teknik Detay:** Sistem, kullanıcı verileri talep edildiğinde yetki seviyelerini doğru bir şekilde doğrulamamaktadır. Standart, düşük seviyeli kullanıcı yetkilerine sahip kimliği doğrulanmış bir saldırgan, bu zafiyeti sömürerek diğer kullanıcıların hassas verilerini sorgulayabilir ve bunlara erişebilir. 

**Etki:** Bu hata, sistemdeki yönetici (admin) hesapları da dahil olmak üzere herhangi bir kullanıcının parola bilgilerine yetkisiz erişime olanak tanımıştır. Dikey hak yükseltme (vertical privilege escalation) yoluyla sistemin tamamen ele geçirilmesi gibi ciddi bir risk oluşturmaktadır.

### [CVE-2024-5619] PruvaSoft Apinizer - Güvensiz Doğrudan Nesne Referansı (IDOR)
**Genel Bakış:** Kullanıcı kontrollü anahtarların, özellikle proje ID değerlerinin güvensiz işlenmesinden kaynaklanan bir Yetkilendirme Atlatma zafiyeti tespit edilmiştir.

**Teknik Detay:** Uygulama, proje indirme talebinde bulunan kullanıcının o spesifik `Proje ID`si için doğru yetkilere sahip olup olmadığını yeterince doğrulamamaktadır. HTTP isteği araya girilerek yakalanıp ID parametresi değiştirildiğinde, yetkilendirme kontrolleri tamamen atlatılabilmektedir.

**Etki:** Bir saldırgan, proje ID'lerini sistematik olarak artırarak (iterate) diğer kullanıcılara veya organizasyonlara ait rastgele proje dosyalarını ve yapılandırmalarını zorla indirebilir. Bu durum, hassas verilerin ve kaynak kodların büyük çapta ifşa olmasına yol açmaktadır.

### [CVE-2024-5620] PruvaSoft Apinizer - Kayıt Uç Noktasında (Endpoint) Hatalı Erişim Kontrolü
**Genel Bakış:** Arka uç (backend) API uç noktalarının ön uç (frontend) güvenlik yapılandırmalarıyla doğru şekilde senkronize edilmediği bir iş mantığı (business logic) ve erişim kontrolü hatası keşfedilmiştir.

**Teknik Detay:** Kullanıcı kayıt özelliği uygulamanın ön yüzünde (UI) açıkça devre dışı bırakılmış ve gizlenmiş olmasına rağmen, arka planda çalışan kayıt API uç noktası aktif kalmış ve uygun yetkilendirme kontrollerinden yoksun bırakılmıştır. 

**Etki:** Bir saldırgan, gizli API uç noktasına doğrudan POST istekleri oluşturup göndererek başarıyla yeni bir kullanıcı hesabı açabilmektedir. Bu durum, yetkisiz tehdit aktörlerinin kendilerine geçerli kimlik bilgileri sağlamasına ve iç sistem ortamına haksız bir ilk erişim (initial access) elde etmesine olanak tanımıştır.

- ##İletişim
**LinkedIn:** [linkedin.com/in/musatalayy](https://linkedin.com/in/musatalayy)
