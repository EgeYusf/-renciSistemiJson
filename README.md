Bu proje, bir öğrenci ve ders yönetim sistemi geliştirmek için tasarlanmıştır. Sistemde öğrenciler, öğretim görevlileri ve dersler arasındaki etkileşimler yönetilir. Kullanıcı, sisteme öğrenci ve öğretim görevlisi ekleyebilir, ders tanımlayabilir ve bu derslere öğrenci ekleyebilir.Sistem Bileşenleri
1. Person (Soyut Sınıf)
Person, "Öğrenci" ve "Öğretim Görevlisi" sınıflarının tümünde kullanılan temel bir soyut sınıftır.
Ortak özellikler:
ID: Kışının benzersiz kimlik numarası.
Name: Kışının adı.
DisplayInfo() adında soyut bir metot içerir.
2. İnterface: ILogin
ILogin, "Öğrenci" ve "Öğretim Görevlisi" sınıflarına sisteme giriş yapma davranışını kazandırmak için kullanılır.
Login() metodunu tanımlar.
3. Ogrenci Sınıfı
Person soyut sınıfından türetilmiştir ve ILogin arayüzünü uygular.
Ekstra özellik:
StudentNumber: Öğrencinin numarası.
DisplayInfo() ve Login() metodlarını gerçekleştirir.
4. OgretimGorevlisi Sınıfı
Person soyut sınıfından türetilmiştir ve ILogin arayüzünü uygular.
Ekstra özellik:
Department: Öğretim görevlisinin bölümü.
SetDepartment(), bölümü belirlemek için kullanılır.
DisplayInfo() ve Login() metodlarını gerçekleştirir.
5. Course (Ders) Sınıfı
Derslerle ilgili bilgileri tutar:
CourseName: Dersin adı.
Credits: Dersin kredisini temsil eder.
Instructor: Dersi veren öğretim görevlisi.
EnrolledStudents: Derse kayıt yaptırılan öğrenciler listesi.
Önemli metodlar:
AddStudent(Ogrenci student): Öğrenciyi derse ekler.
DisplayCourseInfo(): Ders bilgilerini ekrana yazdırır.
6. DataManager Sınıfı
JSON formatında veri kaydetme ve yüklenmesi için kullanılır.
Metodlar:
SaveData<T>(string fileName, List<T> data): Veriyi belirtilen dosyaya kaydeder.
LoadData<T>(string fileName): Dosyadaki veriyi okuyarak liste olarak yükler.
7. Ana Program (Çalıştırma)
Kullanıcının sistemle etkileşimde bulunması için bir menü yapısı sunar:
Menü:
Öğrenci Ekle: Yeni bir öğrenci eklenir ve students.json dosyasına kaydedilir.
Öğretim Görevlisi Ekle: Yeni bir öğretim görevlisi eklenir ve instructors.json dosyasına kaydedilir.
Ders Ekle: Yeni bir ders eklenir ve courses.json dosyasına kaydedilir.
Derse Öğrenci Ekle: Seçilen derse bir öğrenci eklenir.
Ders Bilgilerini Göster: Seçilen dersin bilgileri listelenir.
Öğretim Görevlisi Bölüm Atama: Seçilen öğretim görevlisine yeni bir bölüm atanır.
Listeleme: Öğrenci veya öğretim görevlilerini listeler.
Çıkış: Programdan çıkış yapar.
Program başlatıldığında, veriler otomatik olarak JSON dosyalarından yüklenir (eğer dosyalar mevcutsa).
Yeni veri eklediğinizde, değişiklikler ilgili JSON dosyasına kaydedilir.
Kullanıcı menüden bir seçenek belirlediğinde, sistem gerekli aksiyonları gerçekleştirir.
Döngü, kullanıcı "8. Çıkış" seçeneğini seçene kadar devam eder.
