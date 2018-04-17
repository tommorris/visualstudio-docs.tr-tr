---
title: Hata ayıklayıcı bağlamları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8a9310512417ac0e24046a1b7bcc1fd92099fe98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugger-contexts"></a>Hata ayıklayıcı bağlamları
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama, hata ayıklama altyapısı (DE) aynı anda birçok farklı bağlamları içinde aşağıdaki gibi çalışır:  
  
-   Bir programın yürütme akışında geçerli konumu açıklar kodu bağlamı.  
  
-   Belge bağlamı veya bir kaynak belge içindeki geçerli konumu açıklar konumu.  
  
-   Hangi ifadesinde değerlendirme devre dışı gerçekleşecek bağlam tanımlayan ifade değerlendirme bağlamı.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kod Bağlamı](../../extensibility/debugger/code-context.md)  
 Burada kod yönergeleri, ancak başka bir şekilde tarafından temsil edilebilir değil bugünün çalışma zamanı mimarilerindeki nontraditional diller karşı bir programın yönerge akışında adresi olarak kod bağlam açıklanır.  
  
 [Belge Konumu](../../extensibility/debugger/document-position.md)  
 Visual Studio IDE bilinen bir kaynak dosya konumunda bir soyutlamasını yoluyla hata ayıklama içinde belge konumu tanımlar.  
  
 [Belge Bağlamı](../../extensibility/debugger/document-context.md)  
 Anlatılmaktadır Visual Studio ile ilgili bir kaynak dosyası hata ayıklamaya hangi belge bağlamını temsil eder. Ayrıca simgesi işleyici kodu bağlamı belgelerine bağlamına nasıl eşlendiğini anlatılmaktadır.  
  
 [İfade Değerlendirme Bağlamı](../../extensibility/debugger/expression-evaluation-context.md)  
 Visual Studio'da bir ifade değerlendirme bağlamı hakkında bilgi sağlar. Örneğin, bir yığın çerçevesi ile ilişkili bir ifade değerlendirme bağlamı, yerel değişkenleri, yöntem parametreleri ve sınıf üyeleri değerlendirmek için bağlamı sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata ayıklama kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
 [Hata ayıklama bileşenleri](../../extensibility/debugger/debugger-components.md)  
 Hata ayıklama altyapısı (DE), ifade değerlendiricisi (EE) ve simge işleyici (SH) içeren Visual Studio hata ayıklama bileşenlerini genel bir bakış sağlar.  
  
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.