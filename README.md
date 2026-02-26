# 🪟 PVC Profesyonel Çizim ve Fiyatlandırma Uygulaması

> **Not:** Bu proje ticari/özel bir yazılım olduğu için kaynak kodları **Private (Gizli)** bir depoda tutulmaktadır. Bu depo, projenin mimarisini, yeteneklerini ve kullanılan teknolojileri sergilemek amacıyla (Showcase) oluşturulmuştur.

## 📝 Proje Hakkında
Bu proje, kullanıcıların PVC pencere ve kapı tasarımlarını görsel olarak çizimlerini yapabildiği ve bu tasarımlar üzerinden anlık, dinamik fiyatlandırma alabildiği yerel (local) çalışmak üzere tasarlanmış kapsamlı bir web uygulamasıdır. 

Müşteri taleplerini hızlandırmak, hata payını sıfıra indirmek ve karmaşık fiyat listelerini (Şirket - Fiyat Listesi ilişkileri) sorunsuz yönetmek amacıyla geliştirilmiştir.

## ✨ Temel Özellikler

*   **🎨 Dinamik Görsel Çizim Motoru:** Kullanıcılar pencere veya kapı kanatlarını seçebilir; sağ/sol ve vasistas açılım yönleri seçebilir ve cam ekleyebilir. 
*   **⚡ Anlık Fiyat Hesaplama:** Frontend üzerinde anlık olarak çalışan esnek bir fiyatlandırma algoritması içerir. Seçilen boyut, materyal ve eklentilere göre saniyeler içinde maliyet çıkartır.
*   **🔐 Gelişmiş Güvenlik ve Kimlik Doğrulama:** Özelleştirilmiş JWT (JSON Web Token) altyapısı mevcuttur. "Beni Hatırla" (Remember Me) seçeneğine bağlı olarak değişen spesifik ve güvenli bir Access Token / Refresh Token stratejisi (Spring Security) uygulanmıştır.
*   **🗄️ Kompleks Veri Yönetimi:** Şirket kullanıcıları (`CompanyUser`) ve Fiyat Listeleri (`PriceList`) arasında özel algoritmalarla kurgulanmış ilişkisel DB mimarisi (One-to-Many).

## 💻 Kullanılan Teknolojiler ve Mimari

### Frontend
*   **React.js:** Kullanıcı arayüzü ve dinamik DOM yönetimi.
*   **State Management:** Çizim durumu ve anlık sepet/fiyat takibi için kullandım.
*   *UI Katmanı:* Gelişmiş ve interaktif çizim komponentleri (SVG/CSS tabanlı render).

### Backend
*   **Java & Spring Boot:** Projenin iş mantığı ve RESTful API mimarisi.
*   **Spring Security:** Rol tabanlı erişim kontrolü, özel Register/Authenticate endpoint ayarlamaları.
*   **JWT (JSON Web Token):** Oturum doğrulama altyapısı.

### Veritabanı
*   **Relational Database:** PostgreSQL. Nesne-ilişkisel eşleme (ORM) standartları kullanılarak tasarladım.

## 📸 Ekran Görüntüleri ve Akış

### 1. Görsel Çizim Ekranı ve Parametre Girişi
![Çizim Ekranı](Images/Cizim_Ekrani.png)
*Sağ/Sol açılımlı kanatların görsel olarak tasarlanması.*

### 2. Anlık Fiyatlandırma Sistemi
![Fiyat Hesaplama](Images/Fiyat_Formu_Ekrani.png)
*Tasarlanan ürünün anlık ve detaylı fiyat raporu.*

## 💡 Mimari ve Geliştirme Yaklaşımı / Çözülen Zorluklar

Bu projeyi geliştirirken odağım her zaman yüksek performanslı ve güvenilir bir mimari kurmaktı. Öne çıkan bazı mimari kararlarım:
*   **Güvenlik Stratejisi:** Authentication endpoint'leri (401 hatalarının aşılması, JSON request body handler kuralları) detaylıca yapılandırdım ve token yaşam döngüleri özel bir mantığa bağladım.
*   **Görsel Hiyerarşi:** Çizim sayfasında çizimlerin katman yapısı ile oluşturulması ve bu çizimlerin database'i şişirmemesi adına JSON formatında tutulmasını sağladım.
*   **Fiyat Mimarisi Hizalaması:** Anlık etkileşim gerektiren karmaşık fiyat algoritması, sunucuya sürekli istek atmak yerine hesaplamayı Client (Frontend) tarafında anlık yapacak şekilde kurguladım ve kaynak kullanımı ona göre optimize ettim.

---
**Geliştirici:** Yusuf Harun Canbay
---
Bana ulaşmak veya bu projenin mimarisi hakkında daha fazla konuşmak isterseniz profilimdeki e-posta adresinden veya LinkedIn üzerinden ulaşabilirsiniz.
