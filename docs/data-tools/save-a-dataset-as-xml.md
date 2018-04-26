---
title: Bir veri kümesini XML olarak kaydetme
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 07c0b4b508acf90aac6e65e0a5f4a426bd2fce50
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="save-a-dataset-as-xml"></a>Bir veri kümesini XML olarak kaydetme

XML veri kümesindeki veri kümesine kullanılabilir XML yöntemleri çağırma erişilebilir. Verileri XML biçiminde kaydetmek için ya da çağırabilirsiniz <xref:System.Data.DataSet.GetXml%2A> yöntemi veya <xref:System.Data.DataSet.WriteXml%2A> yöntemi bir <xref:System.Data.DataSet>.

Çağırma <xref:System.Data.DataSet.GetXml%2A> yöntemi XML olarak biçimlendirilir kümesindeki tüm veri tablolardaki verileri içeren bir dize döndürür.

Çağırma <xref:System.Data.DataSet.WriteXml%2A> yöntemi, belirttiğiniz bir dosyaya XML biçimli verileri gönderir.

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>Verileri bir veri kümesini XML olarak bir değişkene kaydetmek için

- <xref:System.Data.DataSet.GetXml%2A> Yöntemi döndürür bir <xref:System.String>. Türünde bir değişken bildirme <xref:System.String> ve sonuçlarını atayın <xref:System.Data.DataSet.GetXml%2A> yöntemi.

     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>Verileri bir veri kümesini XML olarak bir dosyaya kaydetmek için

- <xref:System.Data.DataSet.WriteXml%2A> Yöntemi birçok aşırı yüklemeye sahip. Bir değişken bildirin ve dosyasına kaydetmek için geçerli bir yol atayın. Aşağıdaki kod, verileri bir dosyaya kaydet gösterilmektedir:

     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- [Verileri yeniden veritabanına kaydetme](../data-tools/save-data-back-to-the-database.md)