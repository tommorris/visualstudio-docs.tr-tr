---
title: "Nasıl yapılır: tanımlama ve iş akışı Tasarımcısı'nda aktivite temsilcileri kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
caps.latest.revision: "3"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: 106ef4e7ca41fc181cc305f99e5abfce2abd825e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-define-and-consume-activity-delegates-in-the-workflow-designer"></a>Nasıl yapılır: tanımlama ve iş akışı Tasarımcısı'nda aktivite temsilcileri kullanma
[!INCLUDE[net_v45](../ide/includes/net_v45_md.md)]için yeni bir out-of-box Tasarımcısı içeren <xref:System.Activities.Statements.InvokeDelegate> etkinlik. Bu tasarımcı öğesinden türetilen etkinlik temsilci atamak için kullanılan <xref:System.Activities.ActivityDelegate>, gibi <xref:System.Activities.ActivityAction> veya <xref:System.Activities.ActivityFunc%601>.  
  
### <a name="define-an-activity-delegate"></a>Bir etkinlik temsilci tanımlayın  
  
1.  İçinde [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]seçin **dosya**, **yeni**, **proje**. Seçin **iş akışı** sol düğümünde ve **iş akışı konsol uygulaması** sağdaki şablonu. Proje (isteniyorsa) adı ve'ı tıklatın **Tamam**.  
  
2.  Projeye sağ tıklayın **Çözüm Gezgini** seçip **Ekle**, **yeni öğe...** . Seçin **iş akışı** sol düğümünde ve **etkinlik** sağdaki şablonu. Yeni Etkinlik adı **MyForEach.xaml** tıklatıp **Tamam**. Etkinlik iş akışı Tasarımcısı'nda açılır.  
  
3.  İş Akışı Tasarımcısı'nda tıklayın **bağımsız değişkenleri** sekmesi.  
  
4.  Tıklatın **bağımsız değişkeni oluşturma**. Yeni değişken adı **öğeleri**.  
  
5.  İçinde **bağımsız değişken türü** sütun, select **[T] dizi**.  
  
6.  Türü tarayıcıda seçin **nesne**. Click **Ok**.  
  
7.  Tıklatın **bağımsız değişkeni oluşturma** yeniden. Yeni değişken adı **gövde**. İçinde **yönü** yeni bağımsız değişkeni, select sütun **özelliği**.  
  
8.  Bağımsız değişken türü sütununda seçin **türleri için Gözat...**  
  
9. Türü tarayıcıya girmek **ActivityAction** içinde **türü adı** alan. Seçin **ActivityAction\<T >** ağaç görünümünde. Seçin **nesne** atamak üzere görünür açılır **ActivityAction\<nesnesi >** bağımsız değişkeni için.  
  
10. Sürükleme bir <xref:System.Activities.Statements.While> etkinliğinden **akış denetimi** Tasarımcı yüzeyine araç bölümü.  
  
11. Seçin <xref:System.Activities.Statements.While> etkinliği ve select **değişkenleri** sekmesi.  
  
12. Seçin **değişken oluşturma**. Yeni değişken adı **dizin**.  
  
13. İçinde **değişken türü** sütun, select **Int32**. Bırakın **kapsam** olarak **sırada**ve **varsayılan** sütun boş.  
  
14. Ayarlama **koşulu** özelliği <xref:System.Activities.Statements.While> etkinliğe **dizini < Items.Length;**.  
  
15. Sürükleme bir <xref:System.Activities.Statements.InvokeDelegate> etkinliğinden **Temelleri** Araç Kutusu'na bölümünü **gövde** , <xref:System.Activities.Statements.While> etkinlik.  
  
16. Seçin **gövde** temsilci açılan.  
  
17. İçinde **özellikleri** için kılavuz <xref:System.Activities.Statements.InvokeDelegate> etkinliği tıklatın **...**  düğmesini **temsilci bağımsız değişkenleri** özelliği.  
  
18. İçinde **değeri** adlı bağımsız değişkeni sütun **bağımsız değişkeni**, girin **öğeleri [dizin]**. Tıklatın **Tamam** kapatmak için **DelegateArguments** iletişim.  
  
19. Sürükleme bir <xref:System.Activities.Statements.Assign> altında yatay çizgi üzerine etkinlik <xref:System.Activities.Statements.InvokeDelegate> etkinlik. <xref:System.Activities.Statements.Assign> Etkinlik oluşturulacaktır ve bir <xref:System.Activities.Statements.Sequence> etkinlik otomatik olarak oluşturulur iki etkinlikler içerecek şekilde **gövde** bölümünü **MyForEach** etkinlik. Bu yana sırası gerekli **gövde** bölüm yalnızca tek bir etkinlik içerebilir. Otomatik olarak yeni bir oluşturma <xref:System.Activities.Statements.Sequence> etkinlik özelliğidir yeni [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)].  
  
20. Ayarlama **için** özelliği <xref:System.Activities.Statements.Assign> etkinliğe **dizin**. Ayarlama **değeri** özelliği **atamak** etkinliğe **dizin + 1**.  
  
 Özel **MyForEach** etkinliği artık kez üzerinden içine geçirilen her değer için rasgele bir etkinlik çağırma **öğeleri** etkinliği için girdi olarak koleksiyonundaki değerleri içeren koleksiyon.  
  
### <a name="use-the-custom-activity-in-a-workflow"></a>Özel Etkinlik bir iş akışında kullanma  
  
1.  Tuşuna basarak projeyi oluşturun **Ctrl + Shift + B**.  
  
2.  İçinde **Çözüm Gezgini**, açık **Workflow1.xaml** Tasarımcısı'nda.  
  
3.  Sürükleme bir **MyForEach** araç etkinliğinden Tasarımcı yüzeyine. Etkinlik araç kutusunu projesi olarak aynı ada sahip bir bölümünü olacaktır.  
  
4.  Ayarlama **öğeleri** özelliği **MyForEach** etkinliğe **yeni Object [] {1, "abc"}**.  
  
5.  Sürükleme bir <xref:System.Activities.Statements.WriteLine> etkinliğinden **Temelleri** Araç Kutusu'na bölümünü **temsilci: Body** bölümünü **MyForEach** etkinlik.  
  
6.  Ayarlama **metin** özelliği <xref:System.Activities.Statements.WriteLine> etkinliğe **Argument.ToString()**.  
  
 İş akışı çalıştırıldığında, konsol aşağıdakileri gösterir:  
  
 **1**   
**ABC**