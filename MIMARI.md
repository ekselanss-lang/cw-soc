# CYBERWOLF SOC — Mimari (taslak)

## Teknoloji
- Dil: C++17 / Win32 (mevcut CWPS deneyimi) — tek exe, bağımlılık yok
- Arayüz: yerel web görünümü (Edge/WebView2 yoksa gömülü motor)
- Motor: 127.0.0.1 uzerinde yerel API (CWPS'de kanıtlanan model)

## Katmanlar
1. cekirdek/  : olay veriyolu, görev zamanlayıcı, yapılandırma
2. araclar/   : entegre araç sarmalayıcıları (nmap, masscan, hydra, john, zap-proxy, msf-tarzı modüller)
3. siem/      : olay toplama + korelasyon + gerçek zamanlı uyarı
4. eklenti/   : plugin API (JSON manifest + çalıştırılabilir/komut)
5. kimlik/    : kullanıcı, rol, oturum, denetim izi (audit log)
6. rapor/     : CSV + PDF üretici
7. arayuz/    : masaüstü arayüzü (HTML/CSS/JS + motor)
8. lisans/    : anahtar üretici (satış) + doğrulayıcı (program içi)
9. demo/      : DEMO modu kısıtları (FULL anahtarla açılır)

## Sürüm stratejisi
- DEMO: sınırlı araç/hit, filigran, kayıt teşviki
- FULL: lisans anahtarı ile açılır (offline doğrulama)

## Test kuralı (CWPS dersinden)
Gerçek Windows CI (public repo + şifreli kaynak) — "derlendi" değil "çalıştı" kanıtı.

## Yol haritası
1. İskelet + arayüz kabuğu + motor
2. Araç sarmalayıcıları (nmap/masscan önce)
3. SIEM olay motoru + gerçek zamanlı uyarı
4. Kullanıcı/rol/denetim izi
5. Raporlama (CSV/PDF)
6. Eklenti sistemi
7. Lisans anahtar üretici + DEMO/FULL
8. Inno Setup paketi
