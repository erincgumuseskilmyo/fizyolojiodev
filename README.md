# Temel Veteriner Fizyoloji

GitHub Pages dersin giriş sayfasını sunar. Öğrenci formu, zaman denetimi, Evren değerlendirmesi ve Drive kaydı öğretim elemanının Google Apps Script web uygulamasında çalışır.

## Bağlantıları kurma

1. Google Drive hesabınızda raporlar için yalnızca öğretim elemanlarının erişebildiği bir klasör oluşturun. Klasör bağlantısında `folders/` sonrasında görünen kimliği alın.
2. [Apps Script](https://script.google.com/) üzerinde bağımsız bir proje açın. Bu depodaki `apps-script/Code.gs` içeriğini kod dosyasına, `apps-script/Student.html` içeriğini **Student** adlı HTML dosyasına aktarın.
3. Proje Ayarları → Komut dosyası özellikleri altında `DRIVE_FOLDER_ID` ve `EVREN_API_KEY` değerlerini tanımlayın. Hesabınıza özel model seçmek için isteğe bağlı `EVREN_MODEL` özelliğini kullanabilirsiniz. Varsayılan değer `auto` olur. Evren hesabınızın sohbet API’sine açık olması gerekir.
4. Dağıt → Yeni dağıtım → Web uygulaması seçin. Çalıştıran kullanıcı olarak kendi hesabınızı, erişim için öğrencilerinizi kapsayan seçeneği belirleyin. Kurumsal hesap kullanıyorsanız erişimi kurumla sınırlandırabilirsiniz. Drive ve dış hizmet bağlantısı izinlerini verin. Dağıtımın `/exec` ile biten adresini kopyalayın.
5. Projeyi GitHub deponuzun main veya master dalına gönderin. Settings → Pages → Source altında **GitHub Actions** seçin. Settings → Secrets and variables → Actions → Variables altında **SCRIPT_URL** adlı depo değişkenine web uygulaması adresini girin. Actions sekmesinde **Öğrenci sitesini yayımla** iş akışını çalıştırın. Yayın adresi iş akışının **deploy-pages** çıktısında görünür.
6. Bir deneme öğrencisiyle formu gönderip altı soruyu tamamlayın. Drive klasöründe öğrenci numarası, ad ve soyadla adlandırılmış metin raporunu açın. Apps Script kodunu değiştirirseniz mevcut dağıtımı yeni sürüme güncelleyin.

## Uygulama davranışı

Öğrenci her teslim için bir konu seçer. Bölümlerin alt sınırları sırasıyla 150, 500, 400 ve 200 karakterdir. Her kaynak için künye ve ilgili pasaj istenir. Evren bu bilgilerle konu ve iddia eşleşmesini değerlendirir. Sistem dış kaynakların tam metnini indirmez. Öğrenci kimlik alanları Evren isteğine eklenmez.

Ödev puanı amaç (10), fizyolojik doğruluk (25), bulgular ve uygulama (15), sonuç (10), kaynak kullanımı (10) ölçütlerinden oluşur. Soru süresi sunucuda tutulur. Geç gelen cevap boş sayılır. Aynı sekmede sayfa yenilendiğinde teslim edilmiş oturuma dönülebilir. Yarım kalan sınavın kalan soruları öğrenci geri döndüğünde gösterilir. Tam rapor altıncı soru sonuçlandığında oluşturulur.

Klasördeki `.oturum-` önekli özel dosyalar devam etme ve yeniden deneme için kullanılır. Aynı numarayla ayrı teslimler ayrı dosyalar oluşturur. Öğrenci numarası ve ad-soyad öğrencinin beyanıdır. Rapor ve oturum dosyaları için kurumunuzun saklama süresini uygulayın.
