---
title: Bir veri kümesini XML olarak kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bfea6a97dd5126216d5163dee1dc17e5f6364b46
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632523"
---
# <a name="save-a-dataset-as-xml"></a>Bir veri kümesini XML olarak kaydetme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bir veri kümesini XML olarak kaydetme](https://docs.microsoft.com/visualstudio/data-tools/save-a-dataset-as-xml).  
  
  
XML veri kümesindeki veri kümesinde kullanılabilir XML yöntemleri çağırarak erişilebilir. XML biçiminde verileri kaydetmek için ya da çağırabileceğiniz <xref:System.Data.DataSet.GetXml%2A> yöntemi veya <xref:System.Data.DataSet.WriteXml%2A> yöntemi bir <xref:System.Data.DataSet>.  
  
 Çağırma <xref:System.Data.DataSet.GetXml%2A> yöntemi XML olarak biçimlendirilmiş veri kümesindeki tüm veri tablolardaki verileri içeren bir dize döndürür.  
  
 Çağırma <xref:System.Data.DataSet.WriteXml%2A> yöntemi, belirttiğiniz bir dosyaya XML biçimli verileri gönderir.  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Verileri bir dataset içinde XML olarak bir değişkene kaydetmek için  
  
-   <xref:System.Data.DataSet.GetXml%2A> Yöntemi döndürür bir <xref:System.String>. Bu türde bir değişken bildirmek anlamına gelir <xref:System.String> ve sonuçları atama <xref:System.Data.DataSet.GetXml%2A> yöntemi.  
  
     [!code-csharp[VbRaddataSaving#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#12)]
     [!code-vb[VbRaddataSaving#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#12)]  
  
### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Verileri bir dataset içinde XML olarak bir dosyaya kaydetmek için  
  
-   <xref:System.Data.DataSet.WriteXml%2A> Yöntemi olan çeşitli aşırı yükler. Aşağıdaki kod, verileri bir dosyaya kaydetmek gösterilmektedir. Bir değişken bildirmek ve bir dosyaya kaydetmek için geçerli bir yol atayın.  
  
     [!code-csharp[VbRaddataSaving#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#13)]
     [!code-vb[VbRaddataSaving#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)

