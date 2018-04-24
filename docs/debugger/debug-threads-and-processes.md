---
title: İş parçacıklarında ve işlemlerde hata ayıklama araçları | Microsoft Docs
ms.custom: ''
ms.date: 04/21/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multiprocess debugging
- threading [Visual Studio], debugging
- processes, debugging
- debugging threads
- debugging [Visual Studio], threads
ms.assetid: 9f0c8505-b6b2-452b-adfd-076db14d8115
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f42159b15bbba4bd092dcde34404459212e26ab3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="tools-to-debug-threads-and-processes-in-visual-studio"></a>İş parçacıklarında ve işlemlerde Visual Studio'da hata ayıklama araçları
*İş parçacığı* ve *işlemleri* de bilgisayar bilimi ilgili kavramlar. Her ikisi de belirli bir sırada yürütülmelidir yönergeleri dizisini temsil eder. Ayrı iş parçacıkları veya işlemler,'ndaki yönergeleri ancak, paralel olarak çalıştırabilirsiniz.  
  
 İşlemler işletim sisteminde mevcut ve kullanıcıların program ya da uygulamalar olarak gördükleri için karşılık gelir. Bir iş parçacığı, diğer yandan, bir işlem içinde bulunmaktadır. Bu nedenle, iş parçacığı olarak da adlandırılır *hafif işlemleri*. Her işlem, bir veya daha fazla iş parçacıklarının oluşur.  
  
 Birden çok işlem varlığını aynı anda birden fazla görevi gerçekleştirmek bir bilgisayarın sağlar. Birden çok iş parçacığı varlığını paralel olarak gerçekleştirilecek iş ayırmak bir işlemi etkinleştirir. Birden çok işlemcili bir bilgisayarda, işlemler veya iş parçacıkları farklı işlemciler üzerinde çalıştırabilirsiniz. Bu doğru paralel işleme sağlar.  
  
 Mükemmel bir paralel işleme her zaman mümkün değildir. İş parçacığı bazen eşitlenmelidir. Bir iş parçacığı bir sonuç kümesinden başka bir iş parçacığı için beklemeniz gerekebilir veya bir iş parçacığı başka bir iş parçacığı kullanan bir kaynağa özel kullanım erişimi gerekebilir. Eşitleme, birden çok iş parçacıklı uygulamalarda hatalar ortak bir nedeni sorunlardır. Bazı durumlarda iş parçacığı bekleyen hiçbir zaman kullanılabilir duruma bir kaynağın bitebilir. Bu adlı bir koşul sonuçları *kilitlenme*.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hata ayıklayıcı iş parçacıklarında ve işlemlerde hata ayıklama için güçlü ancak kullanımı kolay araçlar sağlar.  
  
## <a name="tools-and-features"></a>Araçlar ve Özellikler
Kullanmak için ihtiyacınız olan araçları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ne tür kodu, hata ayıklama denediğiniz bağlıdır:

- İşlemleri için kullanılan birincil araçlardır **ekleme işlemi için** iletişim kutusu, **işlemleri** penceresinde ve **hata ayıklama konumu** araç.

- İş parçacığı için iş parçacıklarında hata ayıklama için kullanılan birincil araçlardır **iş parçacığı** penceresinde, iş parçacığı işaretçileri kaynak Windows **Paralel Yığınlar** penceresinde **paralel Gözcü** penceresinde ve **hata ayıklama konumu** araç.  
  
- Kullanan kodu için <xref:System.Threading.Tasks.Task> içinde [görev paralel kitaplığı (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl), [eşzamanlılık çalışma zamanı](/cpp/parallel/concrt/concurrency-runtime/) (yerel kod), çok iş parçacıklı uygulamalarda hata ayıklama için birincil araçlardır**Paralel Yığınlar** penceresinde **paralel Gözcü** penceresinde ve **görevleri** penceresi ( **görevleri** penceresi de destekler JavaScript promise nesnesi).

- GPU iş parçacıklarında hata ayıklama için birincil araçtır **GPU iş parçacıkları** windows.  
  
 Aşağıdaki tabloda kullanılabilir bilgileri gösterir ve her bu konumları gerçekleştirmek eylemler:  
  
|Kullanıcı Arabirimi|Bilgi yok|Gerçekleştirebileceğiniz eylemleri|  
|--------------------|---------------------------|-----------------------------|  
|**İşleme iliştirilemiyor** iletişim kutusu|Kullanılabilir işlemleri ekleyebilirsiniz:<br /><br /> -İşlem adı (.exe)<br />-İşlem kimliği sayısı<br />-Menubar başlığı<br />-Type (yönetilen v4.0; Yönetilen v2.0 v1.1, v1.0; x86; x64; IA64)<br />-Kullanıcı adı (hesap adı)<br />-Oturum sayısı|Eklemek için bir işlem seçin<br /><br /> Uzak bir bilgisayar seçin<br /><br /> Uzak bilgisayarlara bağlanmak için aktarım türünü değiştir|  
|**İşlemler** penceresi|Ekli işlemleri:<br /><br /> -İşlem adı<br />-İşlem kimliği sayısı<br />-.exe işlem yolu<br />-Menubar başlığı<br />-Durumu (sonu. Çalıştıran)<br />-Hata ayıklama (yönetilen, yerel vb.)<br />-Taşıma türü (varsayılan, kimlik doğrulama olmadan yerel)<br />-Aktarım niteleyicisi (uzak bilgisayar)|Araçlar:<br /><br /> -Ekleme<br />-Ayırma<br />-Sonlandırma<br /><br /> Kısayol menüsü:<br /><br /> -Ekleme<br />-Ayırma<br />-Hata ayıklama durduğunda ayırma<br />-Sonlandırma|  
|**İş parçacığı** penceresi|Geçerli işlem iş parçacığı:<br /><br /> -İş parçacığı kimliği<br />-Yönetilen kodu<br />-Kategori (ana iş parçacığı, arabirimi iş parçacığı, uzak yordam çağrısı işleyici veya çalışan iş parçacığı)<br />-İş parçacığı adı<br />-İş parçacığı oluşturulduğu konum<br />-Önceliği<br />-Benzeşim maskesi<br />-Askıya alınmış sayısı<br />-İşlem adı<br />-Bayrağı göstergesi<br />-Askıya alınmış göstergesi|Araçlar:<br /><br /> -Arama<br />-Arama çağrı yığını<br />-Bayrak yalnızca kendi kodum<br />-Bayrağı Özel Modül Seçimi<br />-Göre gruplandırmak<br />-Sütunlar<br />-Genişlet/Daralt callstacks<br />-Grupları Genişlet/Daralt<br />-Dondurma/çözme iş parçacıkları<br /><br /> Kısayol menüsü:<br /><br /> -Kaynağında iş parçacıkları Göster<br />-Bir iş parçacığı geçiş<br />-Çalışan iş parçacığı dondurma<br />-Dondurulmuş bir iş parçacığı çözme<br />-Ek incelemesi için iş parçacığı bayrak<br />-Bir iş parçacığı bayrakla<br />-Bir iş parçacığı yeniden adlandırma<br />-Göster ve iş parçacıkları gizleme<br /><br /> Diğer eylemler:<br /><br /> -Görünüm için bir iş parçacığı bir DataTip, çağrı yığını|  
|Kaynağı penceresi|İş parçacığı göstergeleri sol cilt payı belirtmek tek veya birden çok iş parçacığı (Kapalı kısayol menüsünü kullanarak açık varsayılan **iş parçacığı** penceresi)|Kısayol menüsü:<br /><br /> -Bir iş parçacığı geçiş<br />-Ek incelemesi için iş parçacığı bayrak<br />-Bir iş parçacığı bayrakla|  
|**Konum hata ayıklama** araç çubuğu|-Geçerli işlem<br />-Uygulama askıya alma<br />-Uygulama Sürdür<br />-Askıya alma ve uygulamayı kapatın<br />-Geçerli iş parçacığının<br />-Geçerli iş parçacığı bayrağı Durumu Değiştir<br />-Yalnızca bayraklı iş parçacıkları Göster<br />-Yalnızca geçerli işlem Göster<br />-Geçerli yığın çerçevesi|-Başka bir işleme geçiş<br />-Askıya alma, sürdürme veya uygulamayı kapatın<br />-Geçerli işlemdeki başka bir iş parçacığı geçin<br />-Geçerli iş parçacığının başka bir yığın çerçevesinde geçin<br />-Bayrak veya geçerli iş parçacıklarını bayrakla<br />-Yalnızca bayraklı iş parçacıkları Göster<br />-Yalnızca geçerli işlem Göster|  
|**Paralel Yığınlar** penceresi|-Tek bir pencerede birden çok iş parçacığı için çağrı yığınları.<br />-Her iş parçacığı etkin yığın çerçevesi.<br />-Arayanlar ve herhangi bir yöntem için callees.|-Belirtilen iş parçacıkları filtre<br />-Görevler görünümüne geçin<br />-Bayrak ya da bir iş parçacığı bayrakla<br />-Yakınlaştırma|   
|**Paralel Gözcü** penceresi|-Özel dikkat edilmesi gereken istediğiniz bir iş parçacığı işaretleyebilirsiniz bayrağı sütun.<br />-Bir ok seçili çerçeveyi gösterir çerçeve sütun.<br />-Makine, işlem, kutucuğu, görev ve iş parçacığı görüntüleyebilirsiniz yapılandırılabilir bir sütun.|-Bayrak ya da bir iş parçacığı bayrakla<br />-Yalnızca bayraklı iş parçacığı görüntüle<br />-Anahtar çerçeveler<br />-Bir sütunun sıralama<br />-Grup iş parçacıkları<br />-Donmasına veya iş parçacığı çözme<br />-Paralel Gözcü penceresi verileri dışarı aktarma| 
|**Görevleri** penceresi|-Bilgileri görüntüleyin hakkında <xref:System.Threading.Tasks.Task> görev kimliği, görev durumu dahil olmak üzere nesneleri (zamanlanmış, bekleyen, çalıştığından, karşılıklı), ve hangi iş parçacığının görevi atanır.<br />-Çağrı yığınında geçerli konumu.<br />-Temsilci görevi oluşturma zamanında geçirildi.|-Geçerli görev için geçiş<br />-Bayrak veya bir görev bayrakla<br />-Donmasına veya bir görev çözme|  
|**GPU iş parçacıkları** penceresi|-Özel dikkat edilmesi gereken istediğiniz bir iş parçacığı işaretleyebilirsiniz bayrağı sütun.<br />-Sarı bir ok geçerli iş parçacığının gösterir geçerli iş parçacığı sütunu.<br />- **İş parçacığı sayısı** aynı konumda iş parçacığı sayısını görüntüler sütun.<br />- **Satır** her grup iş parçacığı bulunduğu kod satırını görüntüler sütun.<br />- **Adresi** her grup iş parçacığı bulunduğu yönerge adresi görüntüler sütun.<br />- **Konumu** konumdadır kodu adresinin sütun.<br />- **Durum** sütununda, iş parçacığının etkin ya da engellenen olup olmadığını gösterir.<br />- **Döşeme** iş parçacıklarının döşeme dizini satırda gösterir sütun.|-Farklı bir iş parçacığına değiştirme<br />-Belirli kutucuğu ve iş parçacığı görüntüle<br />-Görüntüle veya bir sütun gizleme<br />-Bir sütuna göre sırala<br />-Grup iş parçacıkları<br />-Donmasına veya iş parçacığı çözme<br />-Bayrak ya da bir iş parçacığı bayrakla<br />-Yalnızca bayraklı iş parçacığı görüntüle|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [GPU kodunda hata ayıklama](../debugger/debugging-gpu-code.md)