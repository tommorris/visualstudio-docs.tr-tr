---
title: "Desteklenmeyen veritabanı sağlayıcıdan bir veritabanı nesnesi seçtiğiniz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 05e638be5cc11f66052e5a1f6116e7205b824106
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>Bir desteklenmeyen veritabanı sağlayıcısı'ndan bir veritabanı nesnesi seçilmedi
O/R Tasarımcısı yalnızca .NET Framework veri sağlayıcısı için SQL Server destekler (<xref:System.Data.SqlClient>). Tıklayabilirsiniz rağmen **Tamam** ve desteklenmeyen bir veritabanı sağlayıcılardan nesnelerle çalışmaya devam etmek için çalışma zamanında beklenmeyen davranışlarla karşılaşabilirsiniz.  
  
> [!NOTE]
>  SQL Server için .NET Framework veri sağlayıcısı kullanan veri bağlantıları desteklenir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
- **Tamam**'ı tıklatın.

   Desteklenmeyen veritabanı sağlayıcısı kullanan bağlantı eşleme varlığı sınıfları tasarlama devam edebilirsiniz. Desteklenmeyen veritabanı sağlayıcıları kullandığınızda beklenmeyen davranışlarla karşılaşabilirsiniz.  
  
     veya  
  
- Tıklatın **iptal**.

   Eylem durdurulur. Oluşturun veya SQL Server için .NET Framework sağlayıcısı kullanan bir veri bağlantısı kullanın.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)