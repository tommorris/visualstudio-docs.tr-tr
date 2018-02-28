---
title: "Kaynak denetimi VSPackage uygulamak kullanılıp belirleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control packages, about source control packages
ms.assetid: 60b3326e-e7e2-4729-95fc-b682e7ad5c99
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 88281496c2e8350f910feda7934e2b55a494243b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="determining-whether-to-implement-a-source-control-vspackage"></a>Kaynak denetimi VSPackage uygulamak kullanılıp belirleme
Bu bölümde, kaynak denetimi uygun tümleştirme yolu seçme hakkında çözümleri ve verir geniş yönergeleri genişletmek için kaynak denetimi eklentilerini ve kaynak denetimi VSPackages seçimleri elaborates.  
  
## <a name="small-source-control-solution-with-limited-resources"></a>Sınırlı kaynaklarla küçük kaynak denetimi çözümü  
 Kaynak denetimi paketi yazma ile ilgili yükünü burdened ve kaynakları sınırlı olursa kaynak denetim eklentisi API tabanlı eklentileri oluşturabilirsiniz. Bu kaynak denetim paketleri yan yana çalışmanıza olanak sağlar ve kaynak denetimi eklentilerini ve isteğe bağlı paketler arasında geçiş yapabilirsiniz. Daha fazla bilgi için bkz: [kaydı ve seçim](../../extensibility/internals/registration-and-selection-source-control-vspackage.md).  
  
## <a name="large-source-control-solution-with-a-rich-feature-set"></a>Büyük miktarlardaki denetim çözümüyle zengin özellik kümesi  
 Kaynak Denetim eklentisi API'sini kullanarak yeterli sayılmaz zengin kaynak denetimi modeli sağlar bir kaynak denetimi çözümünü uygulamak istiyorsanız, bir kaynak denetimi paketi tümleştirme yolu olarak düşünebilirsiniz. Kaynak denetimi bağdaştırıcı (kaynak denetimi eklenti ile iletişim kurar ve temel kaynak denetimi kullanıcı Arabirimi sağlar) paket yerine özellikle değiştirirler özel bir biçimde kaynak denetim olayları işleyebilirsiniz böylece bu kendi geçerlidir. UI denetim ve bu deneyimi korumak istiyorsanız tatmin edici bir kaynak zaten varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bunu kaynak denetim paket seçeneği sağlar. Kaynak denetimi paket genel değildir ve yalnızca ile kullanılmak üzere tasarlanmış [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 Esneklik ve daha zengin denetim Kaynak Denetim mantığı ve UI olanağı sağlayan bir kaynak denetim çözümü uygulamak istiyorsanız, kaynak denetimi paket tümleştirme yolu tercih edebilirsiniz. Şunları yapabilirsiniz:  
  
1.  Kendi kaynak denetimi VSPackage kaydetmek (bkz [kaydı ve seçim](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)).  
  
2.  Varsayılan kaynak denetimi kullanıcı Arabirimi, özel kullanıcı Arabirimi ile değiştirin (bkz [özel kullanıcı arabirimi](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)).  
  
3.  Karakterlerin kullanılması ve Çözüm Gezgini karakter olayları işlemek üzere belirtin (bkz [karakter denetim](../../extensibility/internals/glyph-control-source-control-vspackage.md)).  
  
4.  Sorgu düzenleme ve sorgu kaydetme olayları işlemek (bkz [sorguyu düzenlemek sorgu kaydetmek](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi Oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md)