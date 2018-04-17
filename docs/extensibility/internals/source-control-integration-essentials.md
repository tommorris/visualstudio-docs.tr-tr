---
title: Kaynak denetimi tümleştirmesi Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Source Control Integration, essentials
- Source Control Integration,overview
- essentials, Source Control Integration
ms.assetid: 442057cb-fd54-4283-96f8-2f6dc8bf2de7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0c3e93eb86fdc252f162331033207db5bdaa1569
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="source-control-integration-essentials"></a>Kaynak denetimi tümleştirmesi hakkında temel bilgiler
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Kaynak denetimi tümleştirmesinin iki türlerini destekler: temel işlevleri sağlayan ve kaynak denetimi Eklentisi (önceki adıyla MSSCCI API olarak bilinen) API ve VSPackage tabanlı kaynak denetimi tümleştirmesi çözümü kullanılarak oluşturulan bir kaynak denetimi eklentisi, daha sağlam işlevselliği sağlar.  
  
## <a name="source-control-plug-in"></a>Kaynak Denetimi Eklentisi  
 Kaynak Denetim Eklentisi Kaynak Denetim eklentisi API'yi uygulayan DLL olarak yazılır. Kayıt ve kaynak denetimi tümleştirmesi işlevi API aracılığıyla sağlanır. Bu yaklaşım kaynak denetimi VSPackage kolaydır ve kullandığı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çoğu kaynak denetimi işlemleri için kullanıcı arabirimi (UI).  
  
 Kaynak Denetim eklentisi API kullanarak eklenti bir kaynak denetimi için şu adımları izleyin:  
  
1.  Belirtilen işlevler uygulayan DLL oluşturma [kaynak denetimi eklentileri](../../extensibility/source-control-plug-ins.md).  
  
2.  DLL uygun kayıt defteri girdileri yaparak açıklandığı şekilde kaydedin [nasıl yapılır: kaynak denetimi eklentisi yükleme](../../extensibility/internals/how-to-install-a-source-control-plug-in.md).  
  
3.  Yardımcısı kullanıcı Arabirimi oluşturmak ve kaynak denetimi bağdaştırıcı paketi tarafından istendiğinde görüntüleyin ( [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetim eklentileri aracılığıyla kaynak denetim işlevselliği işleyen bileşeni).  
  
 Daha fazla bilgi için bkz: [kaynak denetim eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md).  
  
## <a name="source-control-vspackage"></a>Kaynak denetimi VSPackage  
 Kaynak denetimi VSPackage uygulama geliştirmek için özelleştirilmiş yenileme sayesinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetim UI. Bu yaklaşım, kaynak denetimi tümleştirmesinin üzerinde tam denetim sağlar. ancak, kullanıcı Arabirimi öğeleri sağlamak ve eklenti yaklaşım altında sağlanması kaynak denetimi arabirimlerini gerektirir.  
  
 Kaynak denetimi VSPackage uygulamak için şunları yapmalısınız:  
  
1.  Oluşturma ve açıklandığı gibi kendi kaynak denetimi VSPackage, kaydetme [kaydı ve seçim](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
2.  Varsayılan kaynak denetimi kullanıcı Arabirimi, özel kullanıcı Arabirimi ile değiştirin. Bkz: [özel kullanıcı arabirimi](../../extensibility/internals/custom-user-interface-source-control-vspackage.md).  
  
3.  Karakterlerin kullanılması ve işlemek için belirtmek **Çözüm Gezgini** karakter olaylar. Bkz: [karakter denetim](../../extensibility/internals/glyph-control-source-control-vspackage.md).  
  
4.  Gösterildiği gibi sorgu düzenleme ve sorgu kaydetme olayları işlemek [sorguyu düzenlemek sorgu kaydetmek](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md).  
  
 Daha fazla bilgi için bkz: [kaynak denetimi VSPackage oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel bakış](../../extensibility/internals/source-control-integration-overview.md)   
 [Kaynak Denetimi Eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [Kaynak Denetimi VSPackage’ı Oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md)