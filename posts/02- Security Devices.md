# Firewalls

Firewall, internal network ile external network arasına yerleştirilen ve aradaki ağ trafiğini denetleyen bir sistemdir. Firewall'lar access control politikasını uygular. Access control en basit haliyle; “kim, hangi kaynağa, hangi şartlar altında erişebilir?” sorusuna verilen cevaptır. Firewall'lar da, "Hangi IP adresleri içeri girebilir?", "Hangi portlardan trafik geçebilir?", "Hangi protokollere izin verilir? (HTTP, SSH, FTP vs.)" gibi sorulara cevap olarak yapılandırılır.

Bununla beraber firewall'lar, yanlış yapılandırıldığında ağda büyük problemlere yol açabilir. Örneğin, izin verilmesi gereken bir protokole izin verilmezse bağlantı sorunları meydana gelebilir. Firewall'lar gelen giden paketleri incelediğinden aynı zamanda ağda performans düşüşüne de sebep olabilir. Ayrıca yetkisiz trafik, meşru trafiğin içine sızarak firewall'lardan geçebilir.

## Firewall Designs

### Private and Public Firewalls

Bu tasarımda public network dış ağ, private network iç ağ olarak kabul edilir. Private network'ten kaynaklanıp public network'ten herhangi bir veri talep eden trafiğe ve o talebe karşılık yanıt olarak public network'ten gelen trafiğe genelde denetlenerek izin verilir. Bunun haricinde public network'ten kaynaklanıp private networke gelen trafik genelde engellenir.

### Demilitarized Zone (DMZ) Firewalls

Genellikle özel ağa bağlı bir iç arayüz, genel ağa bağlı bir dış arayüz ve bir DMZ arayüzünün bulunduğu bir güvenlik duvarı tasarımıdır.

Özel ağdan kaynaklanan trafik, genel veya DMZ ağına doğru ilerlerken denetlenir. Bu trafiğe çok az veya hiç kısıtlama olmadan izin verilir. DMZ veya genel ağdan özel ağa dönen denetlenen trafiğe izin verilir.
DMZ ağından kaynaklanan ve özel ağa giden trafik genellikle engellenir.
DMZ ağından kaynaklanan ve genel ağa giden trafiğe, hizmet gereksinimlerine göre seçici olarak izin verilir.
Genel ağdan kaynaklanan ve DMZ'ye doğru giden trafiğe seçici olarak izin verilir ve denetlenir. Bu tür trafik genellikle e-posta, DNS, HTTP veya HTTPS trafiğidir. DMZ'den genel ağa geri dönen trafiğe dinamik olarak izin verilir.
Genel ağdan kaynaklanan ve özel ağa giden trafik engellenir.

DMZ'nin en büyük avantajı, iç ağdan izole, ayrı bir alan yaratmasıdır. Böylece iç ağa gelen herhangi bir saldırının engellenmesi amaçlanabilir.

### Zone-Based Policy Firewalls

ZPF, firewall kurallarını IP adresine, porta, protokole göre değil; “zone”lara (bölgelere) göre tanımlamana izin verir. 

Ağ segmentleri zone yani bölge bölge ayrılır (inside, outside, DMZ zone vs.). Hangi zone'dan hangi zone'a trafik olacağı tanımlanır. Böylece bu zone'lar arasında hangi protokollere izin verileceğine çeşitli politikalarla karar verilir. Bölge bölge ayrım yapıldığı için, bölgenin içindeki cihazlar arasında akan trafik, firewall'lar tarafından engellenmez.

![image](images/zonebasedfirewalls.png)









