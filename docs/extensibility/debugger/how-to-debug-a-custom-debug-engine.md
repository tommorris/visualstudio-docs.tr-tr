---
title: 'Nasıl yapılır: bir özel hata ayıklama altyapısı hatalarını ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, debugging
- debugging [Debugging SDK], custom debug engines
ms.assetid: df27a8d6-3938-45ff-b47f-b684e80b38a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 95a2db2bc5e8990f536abc851941c337a1dee277
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-a-custom-debug-engine"></a>Nasıl yapılır: bir özel hata ayıklama altyapısı hata ayıklama
Proje türü gelen hata ayıklama altyapısı (DE) başlatan <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> yöntemi. Bu örneği denetiminde DE başlatılır anlamına gelir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje türü denetleme. Ancak, bu örneği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] DE hata ayıklaması yapılamıyor. Hangi aşağıdaki özel DE hata ayıklama olanak tanımak için adımlardır.  
  
> [!NOTE]
>  : "Hata ayıklama bir özel hata ayıklama altyapısı" yordamda kendisine eklemeden önce başlatmak DE beklemeniz gerekir. DE başladığında görüntülenen sizin DE başlangıcına yakın bir ileti kutusu yerleştirin, o noktada ekleyin ve sonra devam etmek için ileti kutusunu temizleyin. Tüm catch bu şekilde DE olayları.  
  
> [!WARNING]
>  Aşağıdaki yordamlar çalışmadan önce yüklenmiş uzaktan hata ayıklama olması gerekir. Bkz: [uzaktan hata ayıklama](../../debugger/remote-debugging.md) Ayrıntılar için.  
  
### <a name="debugging-a-custom-debug-engine"></a>Bir özel hata ayıklama altyapısı hata ayıklama  
  
1.  Msvsmon.exe, uzaktan hata ayıklama İzleyicisi'ni başlatın.  
  
2.  Gelen **Araçları** msvsmon.exe, select menüde **seçenekleri** açmak için **seçenekleri** iletişim kutusu.  
  
3.  "Kimlik doğrulaması" seçeneğini ve tıklayın **Tamam**.  
  
4.  Örneği başlatmak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve özel DE projenizi açın.  
  
5.  İkinci bir örneğini Başlat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve DE başlatır, özel projenizi açın (geliştirme için genellikle VSIP yüklendiğinde, ayarlanmış Deneysel kayıt defteri kovanında budur).  
  
6.  Bu ikinci örneğinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], özel projenizden bir kaynak dosya yükleme ve ayıklanacak programı başlatın. Yüklemek veya bir kesme noktası isabet beklemek DE izin vermek için birkaç dakika bekleyin.  
  
7.  İlk örneğindeki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (DE projenizi ile), seçin **ekleme işlemi için** gelen **hata ayıklama** menüsü.  
  
8.  İçinde **ekleme işlemi için** iletişim kutusu, değişiklik **aktarım** için **(yerel yalnızca kimlik doğrulaması ile) uzaktan**.  
  
9. Değişiklik **niteleyicisi** makinenizi adına (Not: olmadığından girişlerini geçmişini bu ad yalnızca bir kez yazmanız gerekir).  
  
10. İçinde **kullanılabilir işlemler** listesinde, çalıştığını ve tıklatın, DE örneğini seçin **Attach** düğmesi.  
  
11. Simgeler, DE yüklemiş olduğunuz sonra kesme noktaları DE kodunuzda yerleştirin.  
  
12. Durdurun ve yeniden hata ayıklama işlemi her zaman, 6-10 arası adımları yineleyin.  
  
### <a name="debugging-a-custom-project-type"></a>Özel proje türü hata ayıklama  
  
1.  Başlat [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projenizi normal kayıt defteri kovanı ve yükleme (Bu durum, proje türü, bir örnek oluşturma değil, proje türü kaynağına) proje yazın.  
  
2.  Proje özelliklerini açın ve gidin **hata ayıklama** sayfası. İçin **komutu**, yolunu yazın [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE (varsayılan olarak, *[sürücü]*\Program [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 8\Common7\IDE\devenv.exe).  
  
3.  İçin **komut bağımsız değişkenleri**, türü `/rootsuffix exp` (VSIP yüklendiğinde oluşturulan) Deneysel kayıt defteri kovanı için.  
  
4.  Değişiklikleri kabul etmek için **Tamam** 'ı tıklayın.  
  
5.  Proje türü F5 tuşuna basarak başlatın. Bu ikinci bir örneğini başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
6.  Bu noktada, proje türü kaynak kodunda kesme noktaları yerleştirebilirsiniz.  
  
7.  İkinci örneğindeki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], yükleme veya proje türü yeni bir örneğini oluşturun. Yükleme veya oluşturma sırasında noktalarınıza isabet.  
  
8.  Proje türü hata ayıklama.  
  
9. SE başlatmanın işlemde hata ayıklamak seçerseniz, onu başlatıldıktan sonra DE eklemek için "Hata ayıklama bir özel hata ayıklama altyapısı" yordamdaki adımları gerçekleştirebilirsiniz. Bu üç örneklerini verir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çalıştıran: Proje türü kaynağınız, örneklenen proje türü ve sizin DE bağlı Üçüncü saniye için bir tane.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)