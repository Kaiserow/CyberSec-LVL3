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




