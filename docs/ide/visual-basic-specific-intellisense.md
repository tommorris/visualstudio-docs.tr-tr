---
title: "Visual Basic'e özel IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f140a0eaf5d464ec4ead377d86257a8627fd6da4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-basic-specific-intellisense"></a>Visual Basic'e Özel IntelliSense
Visual Basic kaynak kod düzenleyicisinde aşağıdaki IntelliSense özellikleri sunar:  
  
-   Sözdizimi ipuçları  
  
     Sözdizimi ipuçları yazmakta olduğunuz ifadesinin sözdizimi görüntüler. Bu gibi deyimleri için yararlıdır [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).  
  
## <a name="automatic-completion"></a>Otomatik Tamamlama  
  
-   Tamamlanma çeşitli anahtar sözcükleri  
  
     Örneğin, `goto` ve bir boşluk, IntelliSense açılır menüde tanımlanan Etiketler listesi görüntülenir. Desteklenen diğer anahtar sözcükler dahil `Exit`, `Implements`, `Option`, ve `Declare`.  
  
-   Tamamlanma `Enum` ve`Boolean`  
  
     Bir deyim bir numaralandırma üyesine başvurur, IntelliSense üyelerinin listesini görüntüler `Enum`. Ne zaman bir deyim başvurduğu bir `Boolean`, IntelliSense, doğru yanlış aşağı açılan menüsünde görüntülenir.  
  
 Tamamlama açılabilir varsayılan seçimini kaldırarak **otomatik listesi üyeleri** gelen **genel** özellik sayfasında **Visual Basic** klasör.  
  
 Tamamlanma listesi üyeleri, tam sözcüğü veya ALT + sağ ok çağırarak el ile çalıştırabilirsiniz. Daha fazla bilgi için bkz: [kullanarak IntelliSense](../ide/using-intellisense.md).  
  
## <a name="intellisense-in-zone"></a>Bölgedeki IntelliSense  
 IntelliSense bölgesinde yardımcı olur aracılığıyla uygulamaları dağıtmak için ihtiyaç duyan Visual Basic geliştiricileri [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ve kısmi güven ayarlar kısıtlanmıştır. Bu özellik:  
  
-   İle uygulamanın çalıştırılacağı İzinleri seçmenize olanak tanır.  
  
-   Seçilen görüntü API'leri listesi üyeleri kullanılabilir olarak bölge ve ek izinler kullanılamaz olarak gerektiren API'ları görüntüleyin.  
  
 Daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IntelliSense kullanma](../ide/using-intellisense.md)