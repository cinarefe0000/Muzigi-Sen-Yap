 Müziği Sen Yap
PROJE HAKKINDA
Müziği Sen Yap, tarayıcı üzerinde herhangi bir harici oyun motoru veya kütüphaneye ihtiyaç duymadan çalışan,
HTML5 Canvas ve saf JavaScript (Vanilla JS) ile geliştirilmiş 2D ritim ve platform oyunudur.
Oyuncu, ritmik engeller olan müzik notalarının (Do, Re, Mi, Fa, Sol, La, Si) üstünden atlayarak melodi oluşturur,
yerde beliren enstrümanları (Keman ve Piyano) toplayarak puan kazanır. Oyun ilerledikçe hızlanır ve bölüm
geçişleri ile daha dinamik bir tempo sunar.
 TEMEL ÖZELLIKLER
Web Audio API Sentezleyici: Ses dosyası (MP3/WAV) yüklemeden, tamamen kodla dinamik frekanslarda nota
ve efekt sesleri üretir.
Dinamik Bölüm (Stage) Sistemi:
Stage 1 (Keman Sahnesi): Başlangıç temposu, yerdeki kemanları toplama hedefi.
Stage 2 (Piyano Geçidi - 120 Puan Sonrası): Daha hızlı akan platformlar, piyano objeleri ve yüksek tempo.
Prosedürel Ses ve Melodi Akışı: Notaların üstünden her başarılı geçişte bilinen bir şarkının sıradaki notası
otomatik olarak sentezlenerek çalınır.
Tam Duyarlı (Responsive) Tasarım: Tailwind CSS ile hazırlanmış, masaüstü ve mobil cihazlara tam uyumlu
arayüz.
Mobil Dokunmatik Kontroller: Dokunmatik ekranlar için özel Sol/Sağ yön butonları ve Zıpla tuşu.
Görsel Efektler ve Parçacıklar: Skor kazanıldığında, nota aşıldığında veya can kaybedildiğinde yukarı doğru
süzülen renkli metin ve simge efektleri.
 OYUN KONTROLLERI
Eylem Masaüstü (Klavye) Mobil (Dokunmatik)
Zıplama BOŞLUK / ▲ / W ZIPLA Butonu
Sola Hareket ◄ / A ◄ Butonu
Sağa Hareket ► / D ► Butonu
Sesi Aç / Kapat Arayüzdeki Ses İkonu Arayüzdeki Ses İkonu
•
•
◦
◦
•
•
•
•
 TEKNIK MIMARI VE ÇALIŞMA PRENSIBI
1. Oyun Döngüsü (Game Loop)
Oyun, tarayıcının ekran yenileme hızına senkronize çalışan requestAnimationFrame(gameLoop) yapısını
kullanır. Döngü iki ana aşamadan oluşur:
update() : Karakter fiziği (yerçekimi, zıplama), engel ve toplanabilir obje hareketleri, çarpışma kontrolleri
(AABB Collision) ve skor güncellemeleri hesaplanır.
render() : Canvas temizlenir, degrade arka planlar, porte çizgileri (nota çizgileri), oyuncu, engeller, efektler ve
parçacıklar çizilir.
2. Ses Motoru (MusicEngine - Web Audio API)
Oyunda harici ses dosyaları yerine tarayıcının yerleşik AudioContext arabirimi kullanılır:
OscillatorNode ile dalga formları (sawtooth, triangle, sine) oluşturulur.
GainNode ile sesin yüksekliği ve zamanla sönümlenmesi (ADSR zarfı benzeri yapılar) yönetilir.
Frekans tablosu: DO (261.63Hz) ile DO2 (523.25Hz) arasındaki standart nota frekansları tanımlanmıştır.
 KURULUM VE ÇALIŞTIRMA
Oyun tamamen tek bir HTML dosyası içerisinde prototiplenmiştir. Çalıştırmak için:
Projeyi indirin veya kodları bir index.html dosyasına kaydedin.
Dosyaya çift tıklayarak herhangi bir modern web tarayıcısında (Chrome, Firefox, Edge, Safari) açın.
Herhangi bir yerel sunucu (Localhost) veya npm kurulumu gerektirmez.
