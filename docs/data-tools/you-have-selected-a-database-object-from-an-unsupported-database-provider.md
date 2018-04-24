---
title: Bir desteklenmeyen veritabanı sağlayıcısı'ndan bir veritabanı nesnesi seçilmedi
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0646f153149d887ce87f2688d9c28b3da502ba1c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>Bir desteklenmeyen veritabanı sağlayıcısı'ndan bir veritabanı nesnesi seçilmedi

O/R Tasarımcısı yalnızca .NET Framework veri sağlayıcısı için SQL Server destekler (<xref:System.Data.SqlClient>). Tıklayabilirsiniz rağmen **Tamam** ve desteklenmeyen bir veritabanı sağlayıcılardan nesnelerle çalışmaya devam etmek için çalışma zamanında beklenmeyen davranışlarla karşılaşabilirsiniz.

> [!NOTE]
> SQL Server için .NET Framework veri sağlayıcısı kullanan veri bağlantıları desteklenir.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **Tamam**'ı tıklatın.

   Desteklenmeyen veritabanı sağlayıcısı kullanan bağlantı eşleme varlığı sınıfları tasarlama devam edebilirsiniz. Desteklenmeyen veritabanı sağlayıcıları kullandığınızda beklenmeyen davranışlarla karşılaşabilirsiniz.

    -veya-

- Tıklatın **iptal**.

   Eylem durdurulur. Oluşturun veya SQL Server için .NET Framework sağlayıcısı kullanan bir veri bağlantısı kullanın.

## <a name="see-also"></a>Ayrıca bkz.

- [O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)
- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)