---
title: "Nasıl yapılır: bağımsız değişken Tasarımcısı'nı kullanın | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7fe9e4f7a3f4bc603d3f2661b91c5807bea8e4a6
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-the-argument-designer"></a>Nasıl yapılır: bağımsız değişken Tasarımcısı'nı kullanın
Önceki sürümlere göre [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bağımsız değişken Tasarımcısı veri içine ve dışına bir etkinlik akışı izin vermek kolaylaştırır. Tasarımcı tıklayarak erişilen **bağımsız değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Tasarımcı tablo biçiminde görünür ve her sütun üstbilgilerinin dışında sıralanabilir bağımsız değişkenlerin listesini içeren **varsayılan değer** sütun. Her değişken adı, içinde/çıkış /-çıkış/özellik yönü, türü ve varsayılan ifade değeri (varsa) içerir. Ad ve varsayılan ifade değeri düzenlenebilir metin alanları, ve türü ve yön aşağı açılan listeler. Daha fazla bilgi için bkz: [değişkenleri ve bağımsız değişkenler (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).

### <a name="to-create-a-new-argument"></a>Yeni bir değişken oluşturmak için

1.  İş akışı veya etkinlik bir çözüm açın [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Bağımsız değişkenler Tasarımcısı'nı tıklatarak **bağımsız değişkenleri** tasarım tuvale sol alt köşesindeki düğmesi. Bağımsız değişkenler Tasarımcısı görünür.

3.  Etiketli boş satıra tıklayın **bağımsız değişkeni oluşturma**. Bu aşağıdaki varsayılan değerleri kullanarak yeni bir bağımsız değişkeniyle yeni bir satır ekler: argumentx için **adı** x benzersiz bağımsız değişken adları oluşturmak için otomatik olarak arttırılır 1 başlangıç değeri bir tamsayı olduğu **içinde**  için **yönü**, ve **dize** için **bağımsız değişken türü**. Herhangi bir değer için eklenen **varsayılan değer**. İş akışı tasarım işlemi sırasında herhangi bir zamanda bu değerleri değiştirebilirsiniz.

    > [!NOTE]
    > Bağımsız değişken silmek için bağımsız değişken tıklayarak seçin ve tuşuna basarak **silmek** anahtarı.

## <a name="see-also"></a>Ayrıca bkz.

- [İş Akışı Tasarımcısını Kullanma](../workflow-designer/using-the-workflow-designer.md)
- [Değişkenler ve Bağımsız Değişkenler](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)