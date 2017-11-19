---
title: "LINQ-SQL sınıfları O/R Tasarımcısı kullanarak arasında bir ilişki oluşturmak nasıl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: dff1251824a07e8448c6f0dbcf421776d90977a2
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>Nasıl yapılır: LINQ-SQL sınıfları (O/R Tasarımcısı) arasında bir ilişkilendirme oluşturun
Varlık sınıflar arasındaki ilişkileri [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] veritabanındaki tablolar arasında ilişkiler benzer. Kullanarak sınıflar arasındaki ilişkileri oluşturabilirsiniz **ilişkilendirme Düzenleyicisi** iletişim kutusu.  
  
Kullandığınızda, bir üst ve alt sınıf seçmelisiniz **ilişkilendirme Düzenleyicisi** iletişim kutusu bir ilişki oluşturun. Birincil anahtarı içeren varlık sınıfı üst sınıftır; yabancı anahtar içeren varlık sınıfı alt sınıfıdır. Örneğin, sınıflar Northwind müşterileri ve Siparişler tablolarını eşlenen oluşturulmuşsa, müşteri sınıf üst sınıf olur ve sipariş sınıfı alt sınıf olur.  
  
> [!NOTE]
>  Tablodan sürüklediğinizde **Sunucu Gezgini**/**Database Explorer** üzerine [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), ilişkileri otomatik olarak oluşturulan var olan tabanlı veritabanında yabancı anahtar ilişkileri.  

## <a name="association-properties"></a>İlişki özellikleri
O/R Tasarımcısı'nda ilişkilendirme seçtiğinizde bir ilişkilendirme oluşturduktan sonra bazı yapılandırılabilir özellik vardır **özellikleri** penceresi. (Satırın ilgili sınıflar arasındaki ilişkidir.) Aşağıdaki tabloda bir ilişkilendirmenin özellikleri için açıklamalar sağlanır.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Önem düzeyi**|İlişki bire çok veya birebir olup olmadığını denetler.|  
|**Alt özelliği**|Bir koleksiyon veya başvuru ilişki yabancı anahtar taraftaki alt kayıtlarına olan üst bir özellik oluşturulup oluşturulmayacağını belirtir. Örneğin, müşteri siparişi arasındaki ilişki içinde varsa **alt özellik** ayarlanır **True**, siparişleri adlı bir özellik üst sınıf üzerinde oluşturulur.|  
|**Üst özelliği**|İlişkili üst sınıfın başvuran alt sınıf özelliği. Örneğin, müşteri siparişi arasındaki ilişkide bir sipariş için ilişkili müşteri başvuran müşteri adlı bir özellik sipariş sınıfını oluşturulur.|  
|**Katılımcı özellikleri**|İlişki özellikleri görüntüler ve sağlayan bir **üç nokta** yeniden açar (...) düğmesini **ilişkilendirme Düzenleyicisi** iletişim kutusu.|  
|**Benzersiz**|Yabancı hedef sütunlar benzersizlik kısıtlamasını sahip olup olmadığını belirtir.|  
  
## <a name="to-create-an-association-between-entity-classes"></a>Sınıflar arasında bir ilişki oluşturmak için
  
1.  Birleşimdeki üst sınıfın temsil ettiği varlık sınıfı sağ tıklayın, fareyle **Ekle**ve ardından **ilişkilendirme**.  
  
2.  Doğrulayın doğru **üst sınıf** seçildiyse **ilişkilendirme Düzenleyicisi** iletişim kutusu.  
  
3.  Seçin **alt sınıf** açılan kutuya.  
  
4.  Seçin **ilişki özellikleri** sınıfları ilişkilidir. Genellikle, bu veritabanında tanımlı yabancı anahtar ilişkisi eşler. Örneğin, müşteriler ve siparişler ilişkisi içinde **ilişki özellikleri** her sınıf CustomerID şunlardır.  
  
5.  Tıklatın **Tamam** bir ilişki oluşturmak için.  
  
## <a name="see-also"></a>Ayrıca bkz.
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[İzlenecek yol: LINQ-SQL sınıfları oluşturma](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
[LINQ-SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[DataContext yöntemleri (O/R Tasarımcısı)](../data-tools/datacontext-methods-o-r-designer.md)   
[Nasıl yapılır: birincil anahtarlar temsil eder](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)