---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: tanımlama ve etkinlik temsilcileri kullanma'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2039c1792a5e42c3181a01b10ff5bf271ea3bf2f
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755762"
---
# <a name="how-to-define-and-consume-activity-delegates-in-the-workflow-designer"></a>Nasıl yapılır: tanımlama ve iş akışı Tasarımcısı'nda aktivite temsilcileri kullanma

.NET framework 4.5 içeren bir out-of-box Tasarımcısı için <xref:System.Activities.Statements.InvokeDelegate> etkinlik. Bu tasarımcı öğesinden türetilen etkinlik temsilci atamak için kullanılan <xref:System.Activities.ActivityDelegate>, gibi <xref:System.Activities.ActivityAction> veya <xref:System.Activities.ActivityFunc%601>.

## <a name="define-an-activity-delegate"></a>Bir etkinlik temsilci tanımlayın

1.  Visual Studio'da seçin **dosya** > **yeni** > **proje**.

1. İçinde **yeni proje** iletişim kutusunda **iş akışı** solda, kategori ve ardından **iş akışı konsol uygulaması** proje şablonu. Proje (isteniyorsa) adı ve'ı tıklatın **Tamam**.

   > [!NOTE]
   > Görmüyorsanız, **iş akışı** kategori, ilk yükleme **Windows Workflow Foundation** Visual Studio 2017'in bileşeni. Ayrıntılı yönergeler için bkz: [Windows Workflow Foundation yüklemek](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation).

2.  Projeye sağ tıklayın **Çözüm Gezgini** seçip **Ekle** > **yeni öğe**. Seçin **iş akışı** kategori ve ardından **etkinlik** öğe şablonu. Yeni Etkinlik adı **MyForEach.xaml** ve ardından **Tamam**.

   Etkinlik iş akışı Tasarımcısı'nda açılır.

3.  İş Akışı Tasarımcısı'nda tıklayın **bağımsız değişkenleri** sekmesi.

4.  Tıklatın **bağımsız değişkeni oluşturma**. Yeni değişken adı **öğeleri**.

5.  İçinde **bağımsız değişken türü** sütun, select **[T] dizi**.

6.  Türü tarayıcıda seçin **nesne** ve ardından **Tamam**.

7.  Tıklatın **bağımsız değişkeni oluşturma** yeniden. Yeni değişken adı **gövde**. İçinde **yönü** yeni bağımsız değişkeni, select sütun **özelliği**.

8.  Bağımsız değişken türü sütununda seçin **türleri için Gözat**

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

19. Sürükleme bir <xref:System.Activities.Statements.Assign> altında yatay çizgi üzerine etkinlik <xref:System.Activities.Statements.InvokeDelegate> etkinlik. <xref:System.Activities.Statements.Assign> Etkinlik oluşturulur ve bir <xref:System.Activities.Statements.Sequence> etkinlik oluşturulduğunda otomatik olarak iki etkinlikler içerecek şekilde **gövde** bölümünü **MyForEach** etkinlik. Bu yana sırası gerekli **gövde** bölüm yalnızca tek bir etkinlik içerebilir. Otomatik olarak yeni bir oluşturma <xref:System.Activities.Statements.Sequence> etkinlik yeni bir özelliktir .NET Framework 4.5.

20. Ayarlama **için** özelliği <xref:System.Activities.Statements.Assign> etkinliğe **dizin**. Ayarlama **değeri** özelliği **atamak** etkinliğe **dizin + 1**.

   Özel **MyForEach** etkinlik bir kez üzerinden içine geçirilen her değer için rasgele bir etkinlik çağırır **öğeleri** etkinliği için girdi olarak koleksiyonundaki değerleri içeren koleksiyon.

## <a name="use-the-custom-activity-in-a-workflow"></a>Özel Etkinlik bir iş akışında kullanma

1.  Tuşuna basarak projeyi oluşturun **Ctrl**+**Shift**+**B**.

2.  İçinde **Çözüm Gezgini**, açık **Workflow1.xaml** Tasarımcısı'nda.

3.  Sürükleme bir **MyForEach** araç etkinliğinden Tasarımcı yüzeyine. Araç kutusu projesi olarak aynı ada sahip bir bölümünde etkinliktir.

4.  Ayarlama **öğeleri** özelliği **MyForEach** etkinliğe **yeni Object [] {1, "abc"}**.

5.  Sürükleme bir <xref:System.Activities.Statements.WriteLine> etkinliğinden **Temelleri** Araç Kutusu'na bölümünü **temsilci: Body** bölümünü **MyForEach** etkinlik.

6.  Ayarlama **metin** özelliği <xref:System.Activities.Statements.WriteLine> etkinliğe **Argument.ToString()**.

İş akışı çalıştırıldığında, konsol aşağıdaki çıkış şunları gösterir:

**1**
**abc**