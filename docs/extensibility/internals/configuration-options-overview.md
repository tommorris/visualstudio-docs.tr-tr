---
title: "Yapılandırma seçenekleri genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project configurations
- configuration options, about configuration options
ms.assetid: f4ad4dd3-b39e-42df-ad89-d403cdf24a2b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f91f6c3668b7cc1ce881dd0b98d1bd5dddebf530
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="configuration-options-overview"></a>Yapılandırma seçeneklerine genel bakış
Projelerinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] oluşturulabilir, hata ayıklaması, çalıştırma ve/veya dağıtılan birden çok yapılandırmayı destekler. Bir yapılandırma özellikleri, genellikle derleyici anahtarları ve dosya konumları adlandırılmış kümesi ile tanımlanan bir yapı türüdür. Varsayılan olarak, iki yapılandırmaları, hata ayıklama ve yayın yeni çözümler içerir. Bu yapılandırmalar, kendi varsayılan ayarları kullanarak ya da belirli çözüm ve/veya proje gereksinimlerinizi karşılayacak şekilde değiştirilmiş uygulanabilir. Bazı paketler iki şekilde oluşturulabilir: bir ActiveX Düzenleyicisi'ni veya bir yerinde bileşeni olarak. Projeleri ancak birden çok yapılandırmayı destekler gerekmez. Kullanılabilir yalnızca bir yapılandırma varsa, bu yapılandırma tüm çözüm yapılandırmaları eşlenir.  
  
 Yapılandırmalar genellikle iki bölümden oluşur: yapılandırma adı (örneğin hata ayıklama veya yayın gibi) ve platform ayarları. Bir API gibi yapılandırma hedefleri ayarlanan ortam veya işletim sistemi platformu bir yapılandırmasının platform adını tanımlar. Kullanıcıları [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir platform; oluşturulamıyor seçim VSPackage sağlayan bir proje seçmeniz gerekir. Bir kullanıcı yüklemelerini bir VSPackage paket geliştirme sırasında oluşturulan teslim platform istenen herhangi bir platform ad zaman yüzey paket oluşturucusu tarafından ayarlanır ölçütlere göre. Kullanıcı, ardından özellik sayfaları örneği olduğunda VSPackage kullanılabilir hale platformları listesinden seçebilirsiniz.  
  
 Tüm projeleri platformları kavramını destekler beri platform adları isteğe bağlıdır. Bir yapılandırma bir platform ad olmadığında, "Yok" dizesi kullanıcı Arabiriminde görüntülenir.  
  
 Her çözüm yapılandırmaları yalnızca biri aynı anda etkin olabilir, kendi kümesi vardır. Bir çözüm yapılandırması her projeye ait birden fazla yapılandırma kümesidir. "En fazla" artını bir proje çözümü yapılandırmasından dışlamak için seçeneği kaynaklanır. Kullanıcılar kendi özel çözüm yapılandırmaları oluşturabilirsiniz.  
  
 Aşağıdaki tabloda bir proje için yapılandırmalardan Kurulum gösterilmektedir. Satırları yapılandırma adları ve platform adları sütunlarla ile etiketlenir.  
  
|Yapılandırma adı|Platform — Win32|Platform — Win64|  
|------------------------|----------------------|----------------------|  
|Hata ayıklama|\<Win32 ayarlarında hata ayıklama >|\<Hata ayıklama Win64 Ayarları >|  
|Sürüm|\<Win32 ayarları yayın >|\<Win64 ayarları yayın >|  
|MyConfig|Yok|\<MyConfig Win64 Ayarları >|  
  
> [!NOTE]
>  Hedeflediğiniz proje Win32 desteklemiyor sürece, bir "Win32" platform dışlayan "MyConfig" çözüm yapılandırması oluşturulamıyor.  
  
 Bir çözüm için etkin yapılandırmasını değiştirme kümesi yerleşik, çalıştırmak, hata ayıklaması veya dağıtıldığı proje yapılandırmaları, bu çözümde seçer. Hata ayıklama sürümünden etkin çözüm yapılandırmasını değiştirirseniz, örneğin, bu çözüm içindeki tüm projeleri otomatik olarak çözümün hata ayıklama yapılandırmasını da gösterilen projeleri yapılandırma ile oluşturulur. Kullanıcı ortamı Yapılandırma Yöneticisi'nde el ile yapılan değişiklikler yaptı sürece projeleri genellikle de adlandırılmış hata ayıklama bağlantılardır.  
  
 Proje adı, proje yapılandırma adı, bayraklar olup olmadığını oluşturmaya veya dağıtmaya belirtmek için ve platform adı her proje için depolanan çözüm yapılandırma özelliklerini içerir. Daha fazla bilgi için bkz: [çözüm yapılandırması](../../extensibility/internals/solution-configuration.md).  
  
 Kullanıcı görüntülemek ve hiyerarşi (Çözüm Gezgini) çözümü seçme ve özellik sayfaları açarak çözüm yapılandırma parametrelerini ayarlamak. Benzer şekilde, görüntüleyin ve Çözüm Gezgini'nde proje seçerek ve proje özellik sayfalarını açma proje yapılandırma parametrelerini ayarlayın.  
  
 Kullanıcı ayrıca yayın yapılandırma ayarlarını ve geri kalan ile yapılandırma ayarlarında hata ayıklamayı gerekirse kullanarak bir proje oluşturabilirsiniz. Daha fazla bilgi için bkz: [proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md).  
  
 Aşağıdaki diyagramda, çözüm ve proje yapılandırmaları destekler arabirimleri nasıl uygulandığını gösterir:  
  
 ![Yapılandırma arabirimleri grafiği](../../extensibility/internals/media/vsconfiginterfaces.gif "vsConfigInterfaces")  
Yapılandırma arabirimleri  
  
 Önceki diyagrama ilgili birkaç Notlar:  
  
-   `IDispatch`Yapılandırma nesnesinde isteğe bağlı olarak işaretlenir. Özellikle, gözatma nesnesini yapılandırma arabirimlere sahip isteğe bağlıdır.  
  
-   `IVsDebuggableProjectCfg`Yapılandırma nesnesinde isteğe bağlı olarak işaretlenmiş, ancak hata ayıklama desteği için gereklidir.  
  
-   `IVsProjectCfg2`Yapılandırma nesnesinde isteğe bağlı olarak işaretlenmiş, ancak destek gruplandırma çıktı için gereklidir.  
  
-   `Config Provider` Nesnesi, isteğe bağlı bir nesne olarak işaretlenmiş, ancak seçeneğini uygulamak yerdir. Proje nesnesi veya ayrı bir nesne üzerinde nesne uygulayabilir.  
  
-   `IVsCfgProvider2`platform desteği ve yapılandırmasını düzenleme için gereklidir. `IVsCfgProvider`Bu işlevselliği kullanılmaz, yeterli olur.  
  
-   Bazı pratik burada aynı sınıfına ayrı nesneler birleştirilebilir olarak diyagramda gösterildiği bu nesnelerin özel tasarım gereksinimlerinize göre temel. Bu bölümdeki diğer konulara göz ancak, nesneleri ve bu nesnelerle ilişkili arabirimleri diyagramda sunulan senaryo göre incelenecektir.  
  
-   Belirli nesneleri ayrı olarak uygulanır. Örneğin, ayrı iş parçacıkları ve yapı yaşamlarını derleme yapılandırmasını tanımlayan nesnesinden ayrı ayrı yönetmek için nesne üzerinde proje ve çözüm yapı oluşur.  
  
 Yapılandırma nesnesi arabirimleri ve yapılandırma sağlayıcısı nesnesi arabirimleri önceki diyagramda hakkında daha fazla bilgi için bkz: [proje yapılandırma nesnesi](../../extensibility/internals/project-configuration-object.md). Ayrıca, [proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md) yapılandırma oluşturucusu ve yapı bağımlılık nesnesi arabirimleri üzerinde daha fazla bilgi sağlar ve [yönetme dağıtım için proje yapılandırması](../../extensibility/internals/project-configuration-for-managing-deployment.md) Daha fazla yapılandırma dağıtıcı ve dağıtım bağımlılık nesneleri bağlı arabirimler açıklanmaktadır. Son olarak, [çıktı için proje yapılandırması](../../extensibility/internals/project-configuration-for-output.md) çıktı grubu ve çıkış nesnesi arabirimleri ve görüntülemek ve yapılandırmaya bağlı özellikleri ayarlamak için özellik sayfalarının kullanımını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>   
 [Proje yapılandırması oluşturmak için](../../extensibility/internals/project-configuration-for-building.md)   
 [Çözüm Yapılandırması](../../extensibility/internals/solution-configuration.md)