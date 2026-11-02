<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0EA5E9,100:0369A1&height=170&section=header&text=Water%20Reminder%20%F0%9F%92%A7&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=28%20dilde%2C%20maskotlu%20su%20takibi&descAlignY=58&descSize=18" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=19&pause=1300&color=0EA5E9&center=true&vCenter=true&width=620&lines=%F0%9F%8E%AF+Ki%C5%9Fiye+%C3%B6zel+g%C3%BCnl%C3%BCk+su+hedefi;%F0%9F%A6%8A+18+maskot%2C+7+ruh+hali;%F0%9F%8C%8D+28+dil+deste%C4%9Fi;%F0%9F%93%B4+%C3%87evrimd%C4%B1%C5%9F%C4%B1+%C3%A7al%C4%B1%C5%9F%C4%B1r%2C+sonra+e%C5%9Fitler" alt="Typing SVG" />

<br/>

![React Native](https://img.shields.io/badge/React_Native_0.86-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo_SDK_57-000020?style=for-the-badge&logo=expo&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin_Native_Modules-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![RevenueCat](https://img.shields.io/badge/RevenueCat-F25A5A?style=for-the-badge)
![AdMob](https://img.shields.io/badge/AdMob-EA4335?style=for-the-badge&logo=googleadsense&logoColor=white)
![i18next](https://img.shields.io/badge/i18next-28_dil-26A69A?style=for-the-badge&logo=i18next&logoColor=white)

![App Store](https://img.shields.io/badge/App_Store-0D96F6?style=for-the-badge&logo=apple&logoColor=white)
![Google Play](https://img.shields.io/badge/Google_Play-414141?style=for-the-badge&logo=googleplay&logoColor=white)

> 🔒 Kaynak kod private. Bu repo uygulamanın vitrini: özellikler, mimari ve çözülen teknik problemler. Mülakatlarda kod üzerinden anlatmaktan memnuniyet duyarım.

<br/>

<img src="assets/feature-graphic.png" width="640" alt="Water Reminder" />

</div>

---

## 💡 Ne Yapar?

Kilo, boy, yaş, cinsiyet ve aktivite seviyene göre **günlük su hedefini hesaplar**, bardak/şişe ile eklediğin suyu takip eder ve seni seçtiğin **maskotun sesiyle** hatırlatır. 💧 Seriyi (streak) korursan Lumi mutlu, unutursan seni geri çağırır.

---

## ✨ Özellikler

| | Özellik | Ayrıntı |
|:-:|---|---|
| 🎯 | **Kişiye özel hedef** | Kilo, boy, yaş, cinsiyet ve aktiviteye göre önerilen günlük miktar |
| 🥤 | **Hızlı ekleme** | Animasyonlu su şişesi, yüzde ilerleme, bardak/şişe kartları |
| 🦊 | **18 maskot · 7 ruh hali** | SVG silüetler; ortak yüz motoru ilerlemeye göre ifade değiştirir |
| 🔔 | **Akıllı hatırlatma** | 08:00–22:00 arası otomatik aralık veya özel saat listesi; hedef dolunca günün kalanı susar |
| 🔥 | **Seri ve seri kalkanı** | Dün hedef kaçtıysa "serini koru" akışı |
| 📊 | **İstatistik** | Haftalık, aylık, yıllık grafikler |
| 💬 | **Motivasyon desteleri** | Dile göre sunucudan gelen günlük kartlar |
| 📱 | **Android widget** | Ana ekranda günlük ilerleme |
| 📴 | **Çevrimdışı çalışma** | İşlemler kuyruğa alınır, bağlantı gelince Supabase'e eşitlenir |
| 🌍 | **28 dil** | Birimler de yerelleştirilir (kg/cm/ml ve Kiril/Asya kısaltmaları) |
| 💎 | **Premium** | Reklamsız kullanım, tüm maskotlar, tek dokunuşla seri kalkanı |

---

## 🎬 Premium Ekranı

<div align="center">

<img src="assets/paywall.gif" width="260" alt="Paywall" />

</div>

---

## 🏗️ Mimari

```mermaid
flowchart LR
    U[📱 React Native<br/>Expo SDK 57] -->|anonim oturum| SB[(🗄️ Supabase<br/>profil · su günlüğü · içerik)]
    U <--> Q[📴 Offline kuyruk<br/>AsyncStorage]
    Q -->|bağlantı gelince| SB
    U --> N[🔔 Yerel bildirim<br/>cihazda planlama]
    U --> K[⚙️ Kotlin modülleri<br/>exact alarm · widget]
    U --> RC[💳 RevenueCat]
    U --> AD[📢 AdMob]
```

<div align="center">

| Katman | Teknoloji |
|---|---|
| 📱 Uygulama | Expo SDK 57 · React Native 0.86 · React 19 · React Navigation |
| 🌍 Yerelleştirme | i18next · expo-localization · 28 dil |
| 🗄️ Backend | Supabase (anonim auth, PostgreSQL, SQL fonksiyonları) |
| 📴 Çevrimdışı | AsyncStorage kuyruk ve önbellek, artımlı/mutlak eşitleme modları |
| 🔔 Bildirim | expo-notifications (yalnızca yerel planlama, sunucu yok) |
| ⚙️ Native | Kotlin Expo Modules: tam zamanlı alarm, Android ana ekran widget'ı |
| 💳 Gelir | RevenueCat (Premium) · AdMob (ödüllü, geçiş, native, banner) |
| 🧪 Kalite | Jest (24 test dosyası) · ESLint · GitHub Actions CI |
| 🚀 Dağıtım | EAS Build · Expo config plugin'leri (R8, AdMob, bildirim ikonu) |

</div>

---

## 🧠 Çözülen Teknik Problemler

<details>
<summary>📴 <b>Çevrimdışıyken su eklemek ve veri kaybetmemek</b></summary>

<br/>

Bağlantı yokken yapılan su ve profil işlemleri AsyncStorage'daki bir kuyruğa yazılıyor. Çevrimdışına geçmeden önceki sunucu değeri saklanıyor; bağlantı gelince işlemler **artımlı** ya da **mutlak** modda Supabase'e eşitleniyor. Gece yarısında gün değişirse yeni gün kontrolüyle eski günün kaydı yanlış güne yazılmıyor.
</details>

<details>
<summary>🔔 <b>Sunucusuz ama bağlama duyarlı bildirim</b></summary>

<br/>

Hatırlatmalar tamamen cihazda planlanıyor; FCM veya sunucu cron'u yok. Metin, kullanıcının durumuna göre seçiliyor: seri riskteyse akşam uyarısı, öğleden sonra hâlâ 0 ml ise ayrı bir mesaj, seri koptuysa geri çağırma, 3/7/14/30. günlerde kutlama. Her metin seçili maskotun ağzından yazılıyor ve 28 dilde var.
</details>

<details>
<summary>⏰ <b>Android'in hatırlatmaları geciktirmesi</b></summary>

<br/>

Android pil optimizasyonu zamanlanmış bildirimleri kaydırabiliyor. Bunun için Kotlin ile yazılmış bir **Expo native modülü** tam zamanlı alarm iznini ve pil optimizasyonu durumunu kontrol ediyor, gerekirse kullanıcıyı ilgili sistem ayarına yönlendiriyor. Ayrı bir Kotlin modülü günlük ilerlemeyi ana ekran widget'ına yazıyor.
</details>

<details>
<summary>🌍 <b>28 dili bozmadan güncel tutmak</b></summary>

<br/>

Her dil ayrı bir JSON dosyası. CI'daki `check:locales` adımı eksik veya fazla anahtarı ve `{{placeholder}}` sapmalarını yakalayıp build'i kırıyor. Maskot ve ruh hali metin kuralları da ayrı bir kontrolle (`check:lumi`) denetleniyor.
</details>

<details>
<summary>💳 <b>Reklam ve abonelik dengesini korumak</b></summary>

<br/>

Geçiş reklamları sekme değişiminde, bekleme süresi (cooldown) ile gösteriliyor. Zamanlı paywall teklifi haftada en fazla bir kez çıkıyor. Seri kalkanı ile paywall aynı oturumda çakışırsa önce paywall açılıyor; satın alma olursa kalkan otomatik uygulanıyor. Bu kuralların hepsi Jest testleriyle korunuyor.
</details>

---

## 🌍 Diller

`tr` `en` `de` `es` `fr` `it` `pt` `nl` `pl` `ru` `uk` `cs` `ro` `sv` `nb` `ja` `ko` `zh` `zh-Hant` `id` `ms` `vi` `th` `hi` `bn` `te` `ta` `mr`

---

## 🔐 Gizlilik

📄 [Gizlilik politikası ve kullanım koşulları](https://github.com/mertglbyz/Water_Reminder_Support)

---

## 👨‍💻 Geliştirici

<div align="center">

**Mert Gülbeyaz** — Mobile App Developer | AI/ML Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mertglbyz/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/mertglbyz)
[![E-posta](https://img.shields.io/badge/E--posta-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:gulbeyazm6@gmail.com)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0369A1,100:0EA5E9&height=100&section=footer" width="100%" />

</div>
