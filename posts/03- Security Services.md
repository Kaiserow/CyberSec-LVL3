# Traffic Control with ACLs (Access Control List)

ACL'ler, cihazların paketleri, packet header'ındaki bilgilere göre yönlendirmesini ya da droplamasını çeşitli kurallar ile kontrol eder.

ACL'ler ağ trafiğini limitleyerek performansı arttırabilir. Örneğin, bir kuruluşta video trafiğine izin verilmezse, kuruluş ağı, ACL sayesinde video trafiği ile ilişkilendirilen paketleri reddedecek şekilde yapılandırılır ve böylece ağ performansı arttırılır.

Routing güncellemelerinin bilinen bir kaynaktan geldiğinden emin olmak için ACL'ler, routing güncellemelerini kısıtlayabilir. (Routing güncellemesi derken, hedefe giden yoldaki bir değişiklikten bahsediyoruz.

Ağ erişimi için temel düzeyde güvenlik sağlarlar. ACL'ler bir ana bilgisayarın ağın bir bölümüne erişmesine izin verebilir ve başka bir ana bilgisayarın aynı alana erişmesini engelleyebilir. Örneğin, İnsan Kaynakları ağına erişim yetkili kullanıcılarla sınırlandırılabilir.

Üstte de bahsettiğimiz gibi ACL'ler, trafik tipine göre filtreleme yapabilir. Örneğin, e-mail trafiğine izin verirken tüm Telnet trafiğini engelleyebilirler.

Ağ servislerine erişime izin vermek veya erişimi engellemek için ana bilgisayarları tararlar. Örneğin, ACL'ler bir kullanıcının FTP veya HTTP gibi hizmetlere erişmesine izin verebilir veya erişimini engelleyebilir.

Bunların yanında ACL'ler ağ trafiklerini türüne göre önceliklendirebilir.

#### Standart ACLs -> Sadece kaynak IP adresine bakarak karar verir. Hedefle ilgilenmez. Bu yüzden genelde router'ın çıkış arayüzüne yakın yerleştirilir (outbound).
 
#### Extended ACLs -> Kaynak IP + Hedef IP + Protokol + Port numarası gibi daha detaylı kontroller sağlar.

# SNMP (Simple Network Management Protocol)

SNMP, yöneticilerin IP ağı üzerindeki sunucular, iş istasyonları, yönlendiriciler, anahtarlar ve güvenlik cihazları gibi uç cihazları yönetmesine olanak tanır. Ağ yöneticilerinin ağ performansını izlemesini ve yönetmesini, ağ sorunlarını bulup çözmesini ve ağ büyümesini planlamasını sağlar.

SNMP, managers ile agents arasında iletişimi sağlamak için bir mesaj formatı kullanan bir application layer protokolüdür. SNMP manager, SNMP management software çalıştıran, SNMP agent ise trafiği izlenen ve yönetilen anlamlarına gelir.

The Management Information Base (MIB), cihazla ilgili verileri ve operasyonel istatistikleri depolayan, aracılar üzerindeki bir veritabanıdır. Bir ağ aygıtında SNMP'yi yapılandırmak için öncelikle manager ile agent arasındaki ilişkiyi tanımlamak gerekir.

SNMP manager, network management system (NMS)'in bir parçasıdır. SNMP manager, SNMP management yazılımını çalıştırır. SNMP manager'ı "get" eylemini kullanarak bir SNMP agent'ından bilgi toplayabilir ve "set" eylemini kullanarak bir agent'taki yapılandırmaları değiştirebilir. Ayrıca, SNMP agentları "traps" kullanarak bilgileri doğrudan bir network manager'a iletebilir.

# NetFlow

NetFlow, Cisco tarafından geliştirilmiş, günümüzde ise birçok ağ üreticisi tarafından desteklenen bir akış tabanlı ağ izleme protokolüdür. Temel amacı, ağ cihazlarından geçen trafiği kaynak IP adresi, hedef IP adresi, protokol, kaynak ve hedef portlar, servis tipi ve iletilen veri miktarı gibi kriterlere göre akışlara (flows) ayırarak kaydetmek ve analiz edilmesini sağlamaktır. NetFlow sayesinde ağ yöneticileri, ağda kimlerin kimlerle iletişim kurduğunu, hangi uygulamaların yoğunluk oluşturduğunu, anormal trafik desenlerini ve olası güvenlik tehditlerini detaylı bir şekilde görebilir. Bu teknoloji, ağ kapasite planlaması, saldırı tespiti, faturalandırma ve performans yönetimi gibi kritik operasyonel ihtiyaçlar için kullanılır. NetFlow, trafiğin içeriğini değil, trafiğin kimlik ve yön bilgilerini toplar, bu nedenle gizlilik açısından daha güvenli kabul edilir. Zamanla NetFlow'un farklı sürümleri (V5, V9) ve açık standart hale getirilmiş versiyonu olan IPFIX geliştirilmiş, böylece daha esnek veri tipleri ve genişletilebilir formatlar desteklenmiştir. Günümüzde NetFlow, yalnızca Cisco ile sınırlı kalmayıp, Juniper'ın J-Flow'u, Huawei'nin NetStream'i gibi farklı markaların uyumlu çözümleriyle de yaygın bir şekilde kullanılmaktadır.


# Port Mirroring

Packet analyzer, (packet sniffer/traffic sniffer) NIC'e girip çıkan trafiği analiz etmeye yarayan bir yazılımdır. switch, bu giren çıkan trafiğin bir kısmını izole edebilir. Eğer switch trafiği izole ederse, packet sniffer trafiği ham olarak yakalayamaz ve dolayısıyla da düzgün bir analizden söz edilemez. Bunun önüne geçmek için kullanılan yöntem "Port Mirroring"tir.

Port Mirroring (diğer adıyla SPAN - Switched Port Analyzer), bir switch üzerindeki bir porttan (veya VLAN’den) geçen trafiğin birebir kopyalanıp başka bir porta yönlendirilmesi işlemidir. Böylece trafik ham haliyle analiz edilebilir.

# Syslog Servers

Bir ağda belirli olaylar meydana geldiğinde, ağ aygıtlarının yöneticiye ayrıntılı sistem mesajlarıyla bildirimde bulunmak için güvenilir mekanizmaları vardır. Bu mesajlar non-critical veya significant (kayda değer) olabilir. Ağ yöneticilerinin bu mesajları depolamak, yorumlamak, görüntülemek ve ağ altyapısı üzerinde en büyük etkiye sahip olabilecek mesajlar konusunda uyarılmak için çeşitli seçenekleri vardır.

Sistem mesajlarına erişmenin en yaygın yöntemi syslog adı verilen bir protokol kullanmaktır. Routerlar, switchler, application sunucuları, firewall'lar ve diğer ağ aygıtları dahil olmak üzere birçok ağ aygıtı syslog'u destekler. Syslog protokolü, ağ aygıtlarının sistem mesajlarını, ağ üzerinden syslog sunucularına göndermesine olanak tanır.

# NTP (Network Time Protocol)

Ağdaki tüm cihazlarda zamanı senkronize etmek önemlidir çünkü ağları yönetmenin, güvenliğini sağlamanın, sorun gidermenin ve planlamanın tüm yönleri doğru ve tutarlı zaman damgası gerektirir. Zaman, cihazlar arasında senkronize edilmediğinde, ağın farklı bölümlerinde meydana gelen olayların sırasını belirlemek imkansız olacaktır. Bu yüzden, tarih ve saati ayarlamak için iki farklı method kullanılabilir:

• Manual configuration of the date and time

• Configuring the Network Time Protocol (NTP)

Bir ağ büyüdükçe, tüm altyapı cihazlarının senkronize zamanla çalışmasını sağlamak zorlaşır. Daha küçük bir ağ ortamında bile, manuel yöntem ideal değildir. Örneğin, bir cihaz yeniden başlatılırsa, doğru bir tarih ve saat damgası nasıl elde edilebilir?

Bu yüzden de manuel yapılandırmaya daha iyi bir çözüm, ağda NTP'yi yapılandırmaktır. Bu protokol, ağdaki yönlendiricilerin zaman ayarlarını bir NTP sunucusuyla senkronize etmelerine olanak tanır. NTP istemcilerinin zaman ve tarih bilgisini tek bir kaynaktan almaları daha tutarlıdır. 

NTP ağları zaman kaynaklarının hiyerarşik bir sistemini kullanır. Bu hiyerarşik sistemdeki her seviyeye "stratum" olarak adlandırılır. Bir cihazın stratum seviyesi, authoritative (yetkili) zaman kaynağından kaç "atlama" (hop) uzaklıkta olduğunu gösterir. NTP, bu senkronize edilmiş zamanı ağ üzerinde diğer cihazlara dağıtarak çalışır.

## NTP Stratum Levels

### Stratum 0

Bir NTP ağı, zamanı authoritative (yetkili) zaman kaynaklarından alır. Bu yetkili zaman kaynakları, stratum 0 cihazları olarak da adlandırılır (yani aslında stratum 0'da bulunan cihazlar yetkili zaman kaynaklarıdır). Doğru olduğu ve bunlarla ilişkili çok az veya hiç gecikme olmadığı varsayılan yüksek hassasiyetli zaman tutma cihazlarıdır. 

### Stratum 1

Stratum 1 cihazları, yetkili zaman kaynaklarına doğrudan bağlıdır. Birincil network zaman standartı olarak görev alırlar. Yani zamanı doğrudan Stratum 0'dan aldıkları için, ağın geri kalanına zaman senkronizasyonu sağlamakta asıl referans cihazlar olurlar. Örneğin, Stratum 2'ler, 3'ler vs. saatlerini Stratum 1'lerden alır.

### Stratum 2 and lower strata

Stratum 2 sunucuları ağ bağlantıları aracılığıyla stratum 1 cihazlarına bağlanır. NTP istemcileri gibi Stratum 2 cihazları, stratum 1 sunucularından gelen NTP paketlerini kullanarak zamanlarını senkronize eder. Ayrıca stratum 3 cihazları için sunucu olarak da görev yapabilirler.

Stratum numarası ne kadar küçükse, sunucu yetkili zaman kaynağına o kadar yakındır. Stratum numarası büyüdükçe, zaman kaynağından uzaklık da artar. Ağda izin verilen maksimum atlama (hop) sayısı 15'tir. Eğer bir cihaz Stratum 16 seviyesindeyse, bu cihazın zamanla senkronize olmadığını gösterir. Aynı stratum seviyesinde bulunan zaman sunucuları, birbirlerine eş (peer) olarak yapılandırılabilir; böylece hem yedekleme yapılır hem de zaman doğrulaması sağlanabilir.

# AAA Servers

AAA, ağ güvenliğinde kullanılan ve şu üç kelimenin baş harflerinden oluşan bir terimdir:

• Authentication (Kimlik Doğrulama)

• Authorization (Yetkilendirme)

• Accounting (Hesap Tutma)

Kısaca, AAA serverları yukarıdaki 3 işi yapar.

## Authentication

Kullanıcılar ve yöneticiler, kendilerinin söyledikleri kişi olduklarını kanıtlamalıdır. Kimlik doğrulama, kullanıcı adı ve parola kombinasyonları, challenge ve yanıt soruları, token kartları ve diğer yöntemler kullanılarak sağlanabilir.

AAA kimlik doğrulaması, ağa erişimi kontrol etmek için merkezi bir yol sağlar.

## Authorization

Kullanıcı doğrulandıktan sonra, yetkilendirme hizmetleri kullanıcının hangi kaynaklara erişebileceğini ve hangi işlemleri gerçekleştirmesine izin verildiğini belirler. Örneğin, "Kullanıcı 'öğrenci' yalnızca SSH kullanarak ana bilgisayar sunucusu XYZ'ye erişebilir."

## Accounting

Kullanıcının ne yaptığını, neye erişildiğini, kaynağa ne kadar süreyle erişildiğini ve yapılan değişiklikleri kaydeder.
Accounting, ağ kaynaklarının nasıl kullanıldığını takip eder. Örneğin, "Kullanıcı 'öğrenci', 15 dakika boyunca SSH kullanarak XYZ ana bilgisayar sunucusuna erişti."

-------------------------------------------------------------------------------------------------------------------------------

Terminal Access Controller Access-Control System Plus (TACACS+) ve Remote Authentication Dial-In User Service (RADIUS),
her ikisi de AAA sunucularıyla iletişim kurmak için kullanılan authentication protokolleridir.
TACACS+ mı yoksa RADIUS mu seçileceği, kuruluşun ihtiyaçlarına bağlıdır.

Her iki protokol de bir yönlendirici (router) ile AAA sunucuları arasında iletişim kurmak için kullanılabilirken,
TACACS+ daha güvenli bir protokol olarak kabul edilir. Bunun nedeni, TACACS+ protokolündeki tüm veri alışverişlerinin şifrelenmesidir. Oysa RADIUS yalnızca kullanıcının şifresini şifreler. RADIUS, kullanıcı adlarını, accounting bilgilerini veya RADIUS mesajında taşınan diğer bilgileri şifrelemez.

| Özellik | TACACS+ | RADIUS |
|:--------|:--------|:-------|
| **İşlevsellik (Functionality)** | AAA işlevlerini birbirinden ayırır; güvenlik sunucusu uygulamasında modülerlik sağlar. | Kimlik doğrulama ve yetkilendirmeyi birleştirir, muhasebeyi ayırır; daha az esneklik sunar. |
| **Standart (Standard)** | Çoğunlukla Cisco tarafından desteklenir. | Açık/RFC standardı (herkes kullanabilir). |
| **Taşıma Protokolü (Transport)** | TCP kullanır. | UDP kullanır. |
| **CHAP Protokolü (Protocol CHAP)** | Çift yönlü kimlik doğrulama ve yanıt (CHAP) kullanır. | Tek yönlü kimlik doğrulama ve yanıt kullanır. |
| **Gizlilik (Confidentiality)** | Tüm paket şifrelenir. | Sadece kullanıcı şifresi şifrelenir. |
| **Özelleştirme (Customization)** | Router komutları için kullanıcı/grup bazlı yetkilendirme sağlar. | Router komutları için kullanıcı/grup bazlı yetkilendirme yapamaz. |
| **Muhasebe (Accounting)** | Sınırlı muhasebe desteği sağlar. | Geniş muhasebe (accounting) desteği sağlar. |

# VPN (Virtual Private Network)

VPN, genellikle internet gibi public bir ağ üzerinde oluşturulan private bir ağdır.

İlk VPN'ler, kimlik doğrulaması veya verilerin şifrelenmesini içermeyen sadece IP tünelleriydi.

VPN'ler, public ağ üzerinde private bir ağ sağlar. Bunu verileri şifreleyerek yapar. VPN, private bir ağ kullanıdığı için aynı zamanda sanaldır (virtual).

Eskiden sadece belirli bir gruba (community of interest) özel ağ oluşturmak için kullanılan vpn, günümüzde vpnlerin içinde encryption kullanılması vesilesiyle "Virtual private networking" kavramı, VPN with encryption kavramına eş tutulur. VPN'in trafiği şifrelemesi sayesinde "Confidentiality" sağlanır.

En basit anlamıyla, bir VPN, mantıksal bir bağlantı oluşturmak için uzak bir ofis ile merkezi bir ofis gibi iki uç noktayı genel bir ağ üzerinden birbirine bağlar. Mantıksal bağlantılar 2. veya 3. Katmanda yapılabilir.













