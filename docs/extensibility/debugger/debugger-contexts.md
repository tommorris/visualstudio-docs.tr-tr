---
title: "Hata ayıklayıcı bağlamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 809f0f50ace62253371d4fd14425bb870a3be633
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debugger-contexts"></a>Hata ayıklayıcı bağlamları
İçinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hata ayıklama, hata ayıklama altyapısı (DE) aynı anda birçok farklı bağlamları içinde aşağıdaki gibi çalışır:  
  
-   Bir programın yürütme akışında geçerli konumu açıklar kodu bağlamı.  
  
-   Belge bağlamı veya bir kaynak belge içindeki geçerli konumu açıklar konumu.  
  
-   Hangi ifadesinde değerlendirme devre dışı gerçekleşecek bağlam tanımlayan ifade değerlendirme bağlamı.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kod bağlamı](../../extensibility/debugger/code-context.md)  
 Burada kod yönergeleri, ancak başka bir şekilde tarafından temsil edilebilir değil bugünün çalışma zamanı mimarilerindeki nontraditional diller karşı bir programın yönerge akışında adresi olarak kod bağlam açıklanır.  
  
 [Belge konumu](../../extensibility/debugger/document-position.md)  
 Visual Studio IDE bilinen bir kaynak dosya konumunda bir soyutlamasını yoluyla hata ayıklama içinde belge konumu tanımlar.  
  
 [Belge bağlamı](../../extensibility/debugger/document-context.md)  
 Anlatılmaktadır Visual Studio ile ilgili bir kaynak dosyası hata ayıklamaya hangi belge bağlamını temsil eder. Ayrıca simgesi işleyici kodu bağlamı belgelerine bağlamına nasıl eşlendiğini anlatılmaktadır.  
  
 [İfade değerlendirme bağlamı](../../extensibility/debugger/expression-evaluation-context.md)  
 Visual Studio'da bir ifade değerlendirme bağlamı hakkında bilgi sağlar. Örneğin, bir yığın çerçevesi ile ilişkili bir ifade değerlendirme bağlamı, yerel değişkenleri, yöntem parametreleri ve sınıf üyeleri değerlendirmek için bağlamı sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata ayıklama kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
 [Hata ayıklama bileşenleri](../../extensibility/debugger/debugger-components.md)  
 Hata ayıklama altyapısı (DE), ifade değerlendiricisi (EE) ve simge işleyici (SH) içeren Visual Studio hata ayıklama bileşenlerini genel bir bakış sağlar.  
  
 [Hata ayıklama görevleri](../../extensibility/debugger/debugging-tasks.md)  
 Bir program başlatma ve ifadeleri değerlendirme gibi çeşitli hata ayıklama görevlere bağlantılar içerir.