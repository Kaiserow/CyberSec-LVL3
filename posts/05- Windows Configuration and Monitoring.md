# Run as Administrator

Güvenlik açısından en iyi uygulama olarak, Windows'a Yönetici hesabı veya yönetici ayrıcalıklarına (administrator privileges) sahip bir hesap kullanarak oturum açmanız önerilmez. Bunun nedeni, bu ayrıcalıklarla oturum açmışken çalıştırılan herhangi bir programın yönetici ayrıcalıklarını devralmasıdır. Yönetici ayrıcalıklarına sahip kötü amaçlı yazılım, bilgisayardaki tüm dosyalara ve klasörlere tam erişime sahiptir.

# Local Users and Domains

Yeni bir bilgisayarı ilk kez başlattığında veya Windows kurduğunda, senden bir kullanıcı hesabı oluşturman istenir. Bu hesap, yerel kullanıcı (local user) olarak adlandırılır. Bu hesap içerisinde kişisel ayarların, erişim izinlerin, dosya konumların ve kullanıcıya özgü diğer birçok veri saklanır. Bunun dışında Windows, varsayılan olarak iki özel hesap daha oluşturur: Guest (Misafir) ve Administrator (Yönetici) hesapları. Ancak her iki hesap da varsayılan olarak devre dışıdır.

Güvenlik açısından en iyi uygulama, Administrator hesabını etkinleştirmemek ve standart kullanıcılara yönetici ayrıcalıkları vermemektir. Bir kullanıcı, yönetici yetkisi gerektiren bir işlem yapmak istediğinde sistem kullanıcıdan Administrator şifresini ister ve sadece o işlem için yönetici hakları verir. Bu yöntem, bilgisayarda yetkisiz yazılımların kurulmasını, çalıştırılmasını veya dosyalara erişmesini engelleyerek güvenliği artırır.

Guest hesabı da etkinleştirilmemelidir. Guest hesabı, bilgisayarı geçici olarak kullanacak ve kişisel hesabı olmayan kullanıcılar için oluşturulmuştur. Bu hesap şifresizdir ve her oturum açıldığında kullanıcılara varsayılan, sınırlı izinlere sahip bir ortam sunar.

Windows, kullanıcı yönetimini kolaylaştırmak için gruplar kullanır. Bir grup, belirli bir isim ve ona bağlı bir dizi izin içerir. Bir kullanıcı bir gruba eklendiğinde, o grubun tüm izinlerini otomatik olarak alır. Bir kullanıcı birden fazla gruba da eklenebilir ve farklı izin setlerine sahip olabilir. Eğer bir kullanıcı çelişen izinlere sahipse, "açıkça reddet" (explicitly deny) izni her zaman öncelikli kabul edilir ve diğer izinleri geçersiz kılar.

Windows, farklı görevler için birçok yerleşik kullanıcı grubu sunar. Örneğin, Performance Log Users grubu üyelerine performans sayaçlarının kaydını zamanlama ve bu kayıtları yerel veya uzak sistemlerden toplama yetkisi verir. Yerel kullanıcılar ve gruplar, Windows'ta lusrmgr.msc kontrol panel uygulaması üzerinden yönetilir.

Gruplara ek olarak, Windows izinleri ayarlamak için domain (etki alanı) yapısını da kullanabilir. Domain, tüm kullanıcıların, grupların, bilgisayarların, çevre birimlerinin ve güvenlik ayarlarının bir veritabanı üzerinde saklandığı ve bu veritabanı tarafından kontrol edildiği bir ağ hizmeti türüdür. Bu veritabanı, domain controller (DC) adı verilen özel bilgisayarlarda veya bilgisayar gruplarında tutulur.

Domain üzerindeki her kullanıcı ve bilgisayar, oturum açmak ve ağ kaynaklarına erişmek için mutlaka domain controller’a karşı kimlik doğrulaması yapmak zorundadır. Her kullanıcı ve her bilgisayar için geçerli olan güvenlik ayarları, her oturum için domain controller tarafından belirlenir. Domain controller tarafından atanan ayarlar, yerel bilgisayar ya da kullanıcı hesabında tanımlı ayarların üzerinde öncelikli olarak uygulanır.


# CLI and PowerShell


| Özellik | CMD (Command Prompt) | PowerShell |
|:---|:---|:---|
| Çıkış Formatı | Düz metin | Nesne tabanlı |
| Komut Yapısı | Basit komutlar | Gelişmiş cmdlet'ler ve betik desteği |
| Dosya Uzantısı | `.bat`, `.cmd` | `.ps1` |
| Öğrenme Eğrisi | Kolay | Orta - Zor |
| Güç ve Esneklik | Sınırlı | Çok güçlü ve kapsamlı |
| Amaç | Basit yönetim işleri (dosya işlemleri vs.) | Gelişmiş yönetim, otomasyon, sistem yönetimi |
| Desteklediği Komutlar | Eski DOS ve Windows komutları | Eski CMD komutları + yeni cmdlet'ler |
| Hata Yönetimi | Zayıf (temel hata kodları) | Güçlü hata yakalama (`try-catch`) mekanizması |
| Borulama (Pipelining) | Sadece düz metin akışı | Nesne akışı (property bazlı veri işleme) |
| Platform | Sadece Windows | Windows, Linux ve macOS (PowerShell Core) |
| Kullanım Başlangıcı | MS-DOS zamanından beri | Windows PowerShell: 2006, PowerShell Core: 2016+ |

# Özet

- **CMD**, temel komutlar ve hızlı işlemler için idealdir.
- **PowerShell**, karmaşık yönetim işleri, otomasyon ve sistem betikleri için daha uygundur.

# Windows Management Instrumentation (WMI)

WMI, uzak bilgisayarları yönetmek için kullanılır. Bilgisayar bileşenleri, donanım ve yazılım istatistikleri hakkında bilgi alabilir ve uzak bilgisayarların sağlığı izlenebilir.

Günümüzde bazı saldırılar uzak sistemlere bağlanmak, kayıt defterini değiştirmek ve komutları çalıştırmak için WMI kullanır. WMI, yaygın trafik olduğu ve çoğunlukla ağ güvenlik aygıtları tarafından güvenildiği için tespit edilmekten kaçınmalarına yardımcı olur ve uzak WMI komutları genellikle uzak ana bilgisayarda kanıt bırakmaz. Bu nedenle, WMI erişimi kesinlikle sınırlandırılmalıdır.




