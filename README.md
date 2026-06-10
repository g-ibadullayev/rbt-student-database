# 📊 Red-Black Tree Indexed Student Database Simulation

![JavaScript](https://img.shields.io/badge/javascript-%23F7DF1E.svg?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

Bu layihə, böyük verilənlər bazalarında (Database Indexing) axtarış sürətini optimallaşdırmaq üçün istifadə olunan **Qara-Qırmızı Ağac (Red-Black Tree)** alqoritminin vizual və funksional simulyasiyasıdır. 

---

## 🎯 Problemin Təsviri və Mühəndislik Həlli

Əgər tələbə məlumatları ənənəvi bir massivdə (Array/Linked List) saxlansaydı, milyardıncı elementi tapmaq üçün sistem bütün elementləri tək-tək gəzməli olacaqdı ($O(n)$ xətti zaman mürəkkəbliyi). 

Bu layihədə tətbiq olunan **Red-Black Tree İndeksi** sayəsində məlumatlar yaddaşda avtomatik olaraq balanslaşdırılır. Nəticədə, verilənlərin həcmi nə qədər böyük olursa olsun, **Axtarış (Search), Əlavəetmə (Insert) və Silmə (Delete)** əməliyyatları həmişə sabit **$O(\log n)$** zaman mürəkkəbliyi ilə icra olunur.

---

## 📋 Qara-Qırmızı Ağacın Qızıl Qaydaları (Invariants)
Sistem daxilində aşağıdakı balans mexanizmləri tam olaraq tətbiq edilmişdir:
1. Hər bir düyün ya **QIRMIZI**, ya da **QARA**-dır.
2. Kök düyün (Root) həmişə **QARA**-dır.
3. Yeni daxil olan bütün düyünlər **QIRMIZI** başlayır.
4. İki qırmızı düyün alt-alta gələ bilməz (Red-Red Violation). Ağac bunu **Rəng Dəyişmə (Recoloring)** və **Fırlatma (Left/Right Rotation)** ilə həll edir.
5. Kökdən yarpaqlara (NIL) gedən bütün yollarda eyni sayda qara düyün mövcuddur (Black Height).

---

## 🛠️ Layihənin Memarlığı və Kod Strukturu

<details>
<summary><b>💻 JavaScript Motorunu Görmək Üçün Klikləyin (Collapsible Code)</b></summary>

```javascript
// Bayaq hazırladığımız daxili balanslaşdırma və fırlatma kodları bura yerləşir
// leftRotate(x), rightRotate(y), fixInsert(k) mexanizmləri