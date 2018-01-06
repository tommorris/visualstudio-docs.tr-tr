---
title: "Nasıl yapılır: ListObject denetimine yeni bir satır eklendiğinde veri doğrulama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], validating data
- ListObject control, new row
- ListObject control, validating data
ms.assetid: 107bce92-e5ef-40be-8c05-cd6861d39d75
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 87ba8bc1d81dbce4609fcc349337c3f86de50f2d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control"></a>Nasıl Yapılır: ListObject Denetimine Yeni Bir Satır Eklendiğinde Veriyi Doğrulama
  Kullanıcılar için yeni satır ekleyebilir bir <xref:Microsoft.Office.Tools.Excel.ListObject> veriye bağlı denetim. Veri kaynağına değişiklikleri kaydetmeden önce kullanıcının verileri doğrulayabilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="data-validation"></a>Veri doğrulama  
 Her bir satır eklenir bir <xref:Microsoft.Office.Tools.Excel.ListObject> verilere bağlı <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> olayı oluşturulur. Veri doğrulama gerçekleştirmek için bu olayı işleyebilir. Örneğin, uygulamanızın veri kaynağına yalnızca 18 yaş 65 arasındaki olan çalışanlar eklenebilir gerektiriyorsa, satır eklenmeden önce girilen yaşın bu aralığa düştüğünü doğrulayabilirsiniz.  
  
> [!NOTE]  
>  Kullanıcı girişi istemci yanı sıra sunucu üzerindeki her zaman kontrol etmeniz gerekir. Daha fazla bilgi için bkz: [güvenli istemci uygulamaları](/dotnet/framework/data/adonet/secure-client-applications).  
  
#### <a name="to-validate-data-when-a-new-row-is-added-to-data-bound-listobject"></a>Veri ListObject denetimine yeni bir satır verileri doğrulamak için eklenen  
  
1.  Değişkenleri için kimliği oluşturur ve <xref:System.Data.DataTable> sınıf düzeyinde.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#8)]  
  
2.  Yeni bir <xref:System.Data.DataTable> ve örnek sütunlar ve verilerde ekleme `Startup` olay işleyicisi `Sheet1` sınıfı (belge düzeyi projede) veya `ThisAddIn` sınıfında (VSTO eklenti projesindeki).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#9)]  
  
3.  Kodu ekleyin `list1_BeforeAddDataBoundRow` girilen yaş kabul edilebilir aralık içinde olup olmadığını denetlemek için olay işleyicisi.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örneği, mevcut bir sahibi olduğunuzu varsayar <xref:Microsoft.Office.Tools.Excel.ListObject> adlı `list1` bu kodu göründüğü çalışma sayfası üzerinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme Word belgelerini ve Excel çalışma kitaplarını çalışma zamanında VSTO eklentileri](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [ListObject denetimi](../vsto/listobject-control.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)   
 [Nasıl Yapılır: ListObject Sütunlarıyla Verileri Eşleme](../vsto/how-to-map-listobject-columns-to-data.md)  
  
  