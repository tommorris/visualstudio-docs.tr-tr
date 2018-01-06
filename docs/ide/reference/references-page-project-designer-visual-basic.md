---
title: "Başvurular sayfası, Proje Tasarımcısı (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesReference
- vb.ProjectPropertiesUnusedReference
- vb.ProjectPropertiesReferencePaths
helpviewer_keywords:
- References page in Project Designer
- Project Designer, References page
- Unused References dialog box
ms.assetid: 5a47c595-e084-401c-86e1-74e0bf74fd86
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a6fb8d57be1101f8faa5826b2459a9a1658009d9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="references-page-project-designer-visual-basic"></a>Başvurular Sayfası, Proje Tasarımcısı (Visual Basic)
Kullanım **başvuruları** sayfasında **Proje Tasarımcısı** başvuruları, Web başvuruları ve projenizdeki içeri aktarılan ad alanlarını yönetmek için. Proje başvuruları COM bileşenlerini, XML Web Hizmetleri, .NET Framework sınıf kitaplıkları veya derlemeleri veya diğer sınıf kitaplıkları için içerebilir. Başvuruları kullanma hakkında daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](../../ide/managing-references-in-a-project.md).  

 Erişim için **başvuruları** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **proje**, **özellikleri** menü çubuğunda. Proje Tasarımcısı görüntülendiğinde **başvuruları** sekmesi.  

## <a name="uielement-list"></a>UIElement Listesi  
 Aşağıdaki seçenekler seçin veya projenizde başvuruları ve içeri aktarılan ad alanlarını kaldırmak sağlar.  

 **Kullanılmayan başvurular**  
 Erişim için bu düğmeye tıklayın **kullanılmayan başvurular** iletişim kutusu.  

 **Kullanılmayan başvurular** iletişim kutusu, projeye dahil, ancak aslında kod tarafından kullanılan başvuruları kaldırmak sağlar. Listeleyen bir kılavuz içerir **başvuru adı**, **yolu**, kullanılmayan ad alanı başvurularını projenizdeki ilgili ve diğer bilgileri. Kılavuzdaki projenizden kaldırmak ve istediğiniz ad alanı başvurularını seçin **kaldırmak**.  

 **Başvuru yolları**  
 Erişim için bu düğmeye tıklayın **başvuru yollarını** iletişim kutusu.  

> [!NOTE]
>  Proje sistemi bir derleme başvurusu bulduğunda, sistem aşağıdaki sırayla aşağıdaki konumlarda bakarak başvuru çözer:  
>   
>  1.  Proje klasörünü. Proje klasörünü dosyalarını görünür **Çözüm Gezgini** zaman **tüm dosyaları göster** etkin değil.  
> 2.  Belirtilen klasörleri **başvuru yollarını** iletişim kutusu.  
> 3.  Dosyaları görüntülemek klasörleri **Başvuru Ekle** iletişim kutusu.  
> 4.  Projenin obj klasörü. (Bir veya daha fazla derlemeleri COM başvurusu projenize eklediğinizde, projenin obj klasörü eklenebilir.)  

 **Başvuruları**  
 Bu liste, kullanılan projesinde yapılan tüm başvuruları gösterir ya da kullanılmayan.  

 **Ekle**  
 Bir başvuru ya da Web başvuru eklemek için bu düğmeye tıkladığınızda **başvuruları** listesi.  

 Seçin **başvuru** başvurusu başvuru Ekle iletişim kutusunu kullanarak projenize eklemek için.  

 Seçin **Web başvuru** Web başvuru Web Başvurusu Ekle iletişim kutusunu kullanarak projenize eklemek için.  

 **Kaldır**  
 Bir veya daha fazla başvurularında seçin **başvuruları** listeleyin ve ardından silmek için bu düğmeye tıklayın.  

 **Güncelleştirme Web başvurusu**  
 Web başvuru seçin **başvuruları** listesinde ve güncelleştirmek için bu düğmeye tıklayın.  

 **İçeri aktarılan ad alanları**  
 Kendi ad alanı bu kutuya yazın ve'ı tıklatın **ekleme kullanıcı alma** ad alanları listesine eklemek için.  

 Kullanıcı içeri aktarılan ad alanları için diğer adlar oluşturabilirsiniz. Bunu yapmak için diğer ad ve ad biçiminde girin *diğer*=*ad alanı*. Uzun ad alanları, örneğin kullanıyorsanız kullanışlıdır: `Http= MyOrg.ObjectLib.Internet.WebRequestMethods.Http`.  

 **Kullanıcı alma ekleme**  
 Belirtilen ad eklemek için bu düğmeye tıkladığınızda **içeri aktarılan ad alanları** içeri aktarılan ad alanları listesine kutusu. Düğme, yalnızca belirtilen ad zaten listede değilse etkindir.  

 **Ad alanları listesi**  
 Bu liste, tüm kullanılabilir ad alanlarının gösterir. Projenizde dahil olan ad alanları için onay kutularını seçilir.  

 **Güncelleştirme kullanıcı alma**  
 Ad alanları listesinde bir kullanıcı tarafından belirtilen ad alanı seçin, bunu ile değiştirmek istediğiniz adı yazın **içeri aktarılan ad alanları** kutusuna ve ardından yeni ad alanına değiştirmek için bu düğmeyi tıklatın. Düğme yalnızca seçilen ad alanı kullanılarak listeye eklenen ise etkindir **ekleme kullanıcı alma** düğmesi. Ekleyebilirsiniz:  

-   Sınıf veya ad alanları, gibi <xref:System.Math?displayProperty=fullName>.  

-   Gibi diğer alır `VB=Microsoft.VisualBasic`.  

-   XML ad alanları gibi `<xmlns:xsl="http://www.w3.org/1999/XSL/Transform">`.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir projedeki başvuruları yönetme](../../ide/managing-references-in-a-project.md)   
 [Nasıl yapılır: ekleme veya kaldırma içeri aktarılan ad alanlarını (Visual Basic)](../../ide/how-to-add-or-remove-imported-namespaces-visual-basic.md)   
 [Imports Deyimi (XML Ad Alanı)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)
