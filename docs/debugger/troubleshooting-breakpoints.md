---
title: "Visual Studio hata ayıklayıcısında kesme noktaları sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 01/23/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "0"
author: carpediemma
ms.author: emrou
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a59a5448cb9ceb9aa4ac5578e9234c1a9972a15a
ms.sourcegitcommit: 062795f922e7b59fe00d3d95a01a9a8a28840017
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2018
---
# <a name="troubleshoot-breakpoints-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında kesme noktaları sorun giderme

## <a name="breakpoint-warnings"></a>Kesme noktası uyarıları

Hata ayıklama sırasında bir kesme noktası iki visual durumda olabilir: kırmızı bir daire ve boş (beyaz dolu) daire. Hata ayıklayıcı başarıyla hedef işleminde bir kesme noktası belirleyerek mümkün ise, kırmızı bir daire kalır. Kesme noktası simge boş bir daireye ise, kesme devre dışı veya uyarı kesme ayarlanmaya çalışılırken hata oluştu. Farkı belirlemek için kesme getirin ve bir uyarı olup olmadığını görebilirsiniz.

Aşağıdaki iki bölümlerde belirgin uyarılar ve bunları gidermek nasıl açıklanmaktadır. 

### <a name="no-symbols-have-been-loaded-for-this-document"></a>"Hiçbir sembolleri için bu belgenin yüklendi" 

Git **modülleri** penceresi (**hata ayıklama** > **Windows** > **modülleri**) ve modülünüzün olup olmadığını denetleyin yüklendi.  
* Modülünüzün yüklerse denetleyin **simgesi durum** simgeleri yüklenmiş olup olmadığını görmek için sütun. 
  * Simgeler yüklü değil, sorunu tanılamak için simge durumunu denetleyin. Bir modüle bağlam menüsünden **modülleri** penceresinde tıklatın **simge yükleme bilgileri...**  burada deneyin ve simgeleri yüklemek için hata ayıklayıcı Aranan görmek için. Simge yükleme hakkında daha fazla bilgi için bkz: [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  * Simgeler yüklerse, bu PDB, kaynak dosyaları hakkındaki bilgileri içermiyor anlamına gelir. Bu, birkaç olası nedenleri şunlardır: 
    * Kaynak dosyalarınız yakın zamanda eklendiyse, modül güncel bir sürümü yüklü olduğunu onaylayın.  
    * Kırpılmış pdb kullanarak oluşturmak mümkündür **/PDBSTRIPPED** bağlayıcı seçeneği. Kırpılmış pdb kaynak dosya bilgileri içermez. PDB ve bir kırpılmış PDB ile tam çalışma onaylayın.  
    * PDB dosyası kısmen bozuk. Dosya silmeyi deneyin ve bu olmadığını görmek için modülün temiz bir yapı gerçekleştirme sorunu giderir. 

* Modülünüzün yüklü değilse, nedenini bulmak için şunları denetleyin: 
  * Doğru işlem ayıkladığınız onaylayın. 
  * Doğru tür kodu ayıkladığınız denetleyin. Hata ayıklayıcı yapılandırılmış içinde hata ayıklamak için kod türünü bulabilirsiniz **işlemleri** penceresi (**hata ayıklama** > **Windows**  >  **İşlemler**). C# kodunda hata ayıklama çalışıyorsanız, örneğin, .NET Framework'ün uygun bir tür için hata ayıklayıcı yapılandırıldığından emin olun (örneğin, yönetilen (v4\*) yönetilen karşılaştırması (v2\*/v3\*) yönetilen (CoreCLR) karşı). 

### <a name="-the-current-source-code-is-different-from-the-version-built-into"></a>"… Geçerli kaynak kodu yerleşik... sürümünden farklı." 

Kaynak dosya değişti ve kaynak ayıkladığınız kod artık eşleşiyorsa, hata ayıklayıcı kesme noktaları kodda varsayılan olarak ayarlamaz. Bu sorunu normalde, bir kaynak dosya değiştirildi, ancak kaynak kodunu yeniden değildi olur. Bu sorunu gidermek için projeyi yeniden oluşturun. Derleme Sistemi öyle olmadığı halde proje zaten güncel taşıdığını düşündüğü, kaynak dosya yeniden kaydederek ya da yeniden oluşturmanız veya yapı çıktı oluşturulmadan önce projenin temizleme göre proje sistemi zorlayabilirsiniz. 

Nadir senaryolarda eşleşen kaynak kodu gerek kalmadan hata ayıklama isteyebilirsiniz. Bu çok karmaşık bir hata ayıklama deneyimi sağlama, böylece bu nasıl devam etmek istediğinizden emin olun.  

Bu güvenlik denetimleri devre dışı bırakmak için aşağıdakilerden birini yapın: 
* Tek bir kesme noktası değiştirmek için Düzenleyicisi'nde kesme noktası simgenin üzerine getirin ve ayarları (dişli) simgesini tıklatın. Peek penceresi Düzenleyicisi eklenir. Peek penceresinin en üstünde kesme konumunu belirten bir köprü yoktur. Kesme noktası konumunun değiştirilmesine izin verir ve denetlemek için köprüye tıklayın **orijinal olandan farklı olması için kaynak kodu izin**.
* Tüm kesme noktaları için bu ayarı değiştirmek için Git **hata ayıklama** > **seçenekleri ve ayarları**. Üzerinde **hata ayıklama/genel** sayfasında, Temizle **özgün sürümü tam olarak eşleşen kaynak dosyalar gerektiren** seçeneği. İşiniz bittiğinde, bu seçenek yeniden etkinleştirmek emin olun hata ayıklama. 

## <a name="the-breakpoint-was-successfully-set-no-warning-but-didnt-hit"></a>Kesme noktası (uyarı yok) başarıyla ayarlandı, ancak isabet gelmedi 

Bu bölümde, hata ayıklayıcı tüm uyarılar görüntülemiyorsa – kesme kırmızı bir daire etkin hata ayıklama sırasında yine de kesme noktası isabet değil, sorunları gidermek için bilgiler sağlar. 

Denetlenecek bazı noktalar şunlardır: 
1. Kodunuzu birden fazla işlem veya birden çok bilgisayarda çalışıyorsa, doğru işlem ya da bilgisayar ayıkladığınızı emin olun.  
2. Kodunuzu çalışır durumda olduğunu doğrulayın. Bu şekilde test etmek kolay bir çağrı ekleyin etmektir `System.Diagnostics.Debugger.Break` (C# /VB) veya `__debugbreak` (C++) satırına kod burada çalıştığınız kesme noktası ayarlayın ve projenizi yeniden derleyin. 
3. Hata ayıklama en iyi duruma getirilmiş kodu varsa, emin olun, kesme noktası ayarlandığı işlevi olan değil başka bir işleve içermesinden. `Debugger.Break` Önceki iade açıklanan test, bu da test etmek için çalışabilir. 

## <a name="i-deleted-a-breakpoint-but-i-continue-to-hit-it-when-i-start-debugging-again"></a>Bir kesme noktası silinmiş, ancak hata ayıklamayı yeniden başlattığınızda isabet devam 

Hata ayıklama sırasında bir kesme noktası sildiyseniz, hata ayıklama yeniden başlattığınızda kesme noktası isabet. Bu kesme basarsa durdurmak için tüm kesme örneklerini kaldırılma olduğundan emin olun **kesme noktaları** penceresi.  
