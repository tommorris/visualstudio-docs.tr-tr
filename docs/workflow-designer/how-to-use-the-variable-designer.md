---
title: "Nasıl yapılır: değişken Designer'ı kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
caps.latest.revision: "14"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: c9bf63222f16e29044a9a07078096b765421fbb3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-variable-designer"></a>Nasıl yapılır: değişken Tasarımcısı'nı kullanın
Değişken Tasarımcısı'nı kullanmak için değişkenler veri bağlama senaryoları ve koşullu deyimler oluşturmak için kullanılır. Tasarımcı tıklayarak erişilen **değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Tasarımcı tablo biçiminde görünür ve her sütun üstbilgilerinin dışında sıralanabilir değişkenlerin listesini içeren **varsayılan** sütun. Her bir değişken adı, değişken türü, kapsamı ve varsayılan değer (varsa) içerir. Ad ve varsayılan değer düzenlenebilir metin alanları, ve türüne ve kapsamına aşağı açılan listeler. Değişken Tasarımcısı çağrıldığında seçtiğiniz etkinlik kapsamıdır. Bir değişken seçimi kapsamı içinde oluşturulamaz, kapsam, kapsamında oluşturulan değişkenler izin veren Seçimi en yakın üst öğede etkinliğini varsayılır. [! DAHİL[crabout](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).  
  
 Kullanıcının açık olarak sıralama denetimleri birini kullanır, kapatır ve değişken Tasarımcısı'nı açana veya başka bir değişken oluşturur kadar sıralama düzenini uygulanmıyor.  
  
### <a name="to-create-a-new-variable"></a>Yeni bir değişken oluşturmak için  
  
1.  İş akışı veya etkinlik bir çözüm açın [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
2.  Tasarım tuval üzerinde bir etkinlik akışınıza seçin.  
  
3.  Değişken Tasarımcısı'nı tıklatarak **değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Değişken Tasarımcısı görünür.  
  
4.  Etiketli boş satıra tıklayın **oluşturma değişken**. Bu aşağıdaki varsayılan değerleri kullanarak yeni bir değişken ile yeni bir satır ekler: variablex için **adı** x benzersiz değişken adları oluşturmak için otomatik olarak arttırılır 1 başlangıç değeri bir tamsayı olduğu  **Dize** için **değişken türü**, ve **dizisi** için **kapsam**. Herhangi bir değer için eklenen **varsayılan**. İş akışı tasarım işlemi sırasında herhangi bir zamanda bu değerleri değiştirebilirsiniz.  
  
    > [!NOTE]
    >  Bir değişkeni silmek için değişkeni tıklayarak seçin ve tuşuna basarak **silmek** anahtarı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İş Akışı Tasarımcısı'nı kullanarak](../workflow-designer/using-the-workflow-designer.md)   
 [Değişkenleri ve bağımsız değişkenler](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)   
 [Nasıl Yapılır: Bağımsız Değişken Tasarımcısını Kullanma](../workflow-designer/how-to-use-the-argument-designer.md)