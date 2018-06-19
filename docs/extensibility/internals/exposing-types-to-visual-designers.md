---
title: Görsel tasarımcılar türlerine gösterme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 28dcc17c74a5b5ef3c9784fafe972beb6f170d90
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135980"
---
# <a name="exposing-types-to-visual-designers"></a>Görsel tasarımcılar türlerine gösterme
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sınıf ve tür tanımları tasarım zamanında bir görsel tasarımcı görüntülemek için erişiminiz olmalıdır. Sınıflar (başvuruları ve bağımlılıklarını) geçerli projenin tamamını bağımlılık kümesini içeren derlemeler önceden tanımlanmış kümesinden yüklenir. Ayrıca visual tasarımcıları için gerekli erişim sınıfları ve özel araçları tarafından oluşturulan dosyalarda tanımlı türleri olabilir.  
  
 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] Ve [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] proje sistemleri üretilen sınıfları ve türleri geçici taşınabilir erişmek için destek sağlar yürütülebilir dosyalar (geçici PEs). Böylece türleri Bu derlemelerden yüklenen ve tasarımcıları için gösterilen özel bir aracı tarafından oluşturulan herhangi bir dosya geçici bir derlemeye derlenebilir. Her özel aracın çıktısının ayrı bir geçici PE'ye derlenir ve başarı veya başarısızlık bu geçici derlemesinin yalnızca olsun veya olmasın oluşturulan dosya derlenebilir üzerinde bağlıdır. Bir projeyi bir bütün olarak derleme değil olsa da, tek tek geçici PEs tasarımcılarına kullanılabilir olabilir.  
  
 Bu değişiklikler özel araç çalıştırılırken sonucunu olması koşuluyla proje sistemi özel bir araç ve çıktı dosyası için değişiklik izleme için tam destek sağlar. Özel araç her çalıştırıldığında yeni bir geçici PE oluşturulur ve uygun bildirimleri tasarımcıları için gönderilir.  
  
> [!NOTE]
>  Geçici program yürütülebilir oluşturma dosyası arka planda gerçekleşir olduğundan, derleme başarısız olursa hata kullanıcıya raporlanır.  
  
 Geçici PE desteğinden özel araçlar aşağıdaki kurallara uymalıdır:  
  
-   `GeneratesDesignTimeSource` Kayıt defterinde 1 olarak ayarlanması gerekir.  
  
     Hiçbir program yürütülebilir dosya derleme, bu ayar olmadan gerçekleşir.  
  
-   Oluşturulan kodun genel proje ayarı ile aynı dilde olmalıdır.  
  
     Geçici PE ne özel araç istenen uzantı olarak raporlar bağımsız olarak derlenmiş <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> koşuluyla `GeneratesDesignTimeSource` kayıt defterinde 1 olarak ayarlayın. Uzantı .vb, .cs veya .jsl olması gerekmez; Bu uzantıyı olabilir.  
  
-   Özel aracı tarafından oluşturulan kodu geçerli olmalıdır ve yalnızca başvuruları projede mevcut kümesini kendi kullanarak aynı anda derleme gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> bittikten yürütülüyor.  
  
     Geçici PE'nin derlendiğinde derleyiciye sağlanan yalnızca kaynak özel araç çıktısını dosyasıdır. Bu nedenle, geçici PE'nin kullanan özel bir araç projedeki diğer dosyaların bağımsız olarak derlenmiş çıktı dosyaları oluşturmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BuildManager nesnesine giriş](http://msdn.microsoft.com/en-us/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [Tek dosya oluşturucuları uygulama](../../extensibility/internals/implementing-single-file-generators.md)   
 [Tek Dosya Oluşturucuları Kaydetme](../../extensibility/internals/registering-single-file-generators.md)