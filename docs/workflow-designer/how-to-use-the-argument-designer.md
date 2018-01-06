---
title: "Nasıl yapılır: bağımsız değişken Tasarımcısı'nı kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: aa1cdd0dd563a5f87d4e32f779985afd63319032
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-argument-designer"></a>Nasıl yapılır: bağımsız değişken Tasarımcısı'nı kullanın
Önceki sürümlere göre [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bağımsız değişken Tasarımcısı veri içine ve dışına bir etkinlik akışı izin vermek kolaylaştırır. Tasarımcı tıklayarak erişilen **bağımsız değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Tasarımcı tablo biçiminde görünür ve her sütun üstbilgilerinin dışında sıralanabilir bağımsız değişkenlerin listesini içeren **varsayılan değer** sütun. Her değişken adı, içinde/çıkış /-çıkış/özellik yönü, türü ve varsayılan ifade değeri (varsa) içerir. Ad ve varsayılan ifade değeri düzenlenebilir metin alanları, ve türü ve yön aşağı açılan listeler. [! DAHİL[crabout](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).  
  
### <a name="to-create-a-new-argument"></a>Yeni bir değişken oluşturmak için  
  
1.  İş akışı veya etkinlik bir çözüm açın [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
2.  Bağımsız değişkenler Tasarımcısı'nı tıklatarak **bağımsız değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Bağımsız değişkenler Tasarımcısı görünür.  
  
3.  Etiketli boş satıra tıklayın **bağımsız değişkeni oluşturma**. Bu aşağıdaki varsayılan değerleri kullanarak yeni bir bağımsız değişkeniyle yeni bir satır ekler: argumentx için **adı** x benzersiz bağımsız değişken adları oluşturmak için otomatik olarak arttırılır 1 başlangıç değeri bir tamsayı olduğu **içinde**  için **yönü**, ve **dize** için **bağımsız değişken türü**. Herhangi bir değer için eklenen **varsayılan değer**. İş akışı tasarım işlemi sırasında herhangi bir zamanda bu değerleri değiştirebilirsiniz.  
  
    > [!NOTE]
    >  Bağımsız değişken silmek için bağımsız değişken tıklayarak seçin ve tuşuna basarak **silmek** anahtarı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Akışı Tasarımcısı'nı kullanarak](../workflow-designer/using-the-workflow-designer.md)   
 [Değişkenler ve Bağımsız Değişkenler](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)