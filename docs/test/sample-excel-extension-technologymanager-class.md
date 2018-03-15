---
title: "Örnek Excel uzantısı: TechnologyManager Sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bb6fe0e966035945a5af6ee7d9d3ae056f18ca3c
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="sample-excel-extension-technologymanager-class"></a>Örnek Excel Uzantısı: TechnologyManager Sınıfı

Bu sınıfını genişleten <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> sınıfı ve Çekirdek Hizmetleri için sağlamaktan sorumludur [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] uzantısı. Taban sınıfı birçok yöntem olsa da, bu örnekte yalnızca bir alt kümesini kullanılır.

 Bazı yöntemleri yalnızca bir özellik değeri döndürür. Birçok yöntem algoritmaları kodlanmış UI test motoruna yapı varsayılan değerini geçersiz kılması Geliştirici izin verecek şekilde tasarlanmıştır. Bu yöntemler throw bir <xref:System.NotSupportedException> veya return `null`, varsayılan algoritma kullanılacak framework söyler.

 Temel alınan teknoloji karmaşıklığına bağlı olarak, teknoloji Yöneticisi kodunun geliştirilmesi için birkaç ay birkaç hafta ila ele geçirebilir. Excel, potansiyel olarak çok kapsamlı teknoloji Yöneticisi oluşturma olanağı sağlar. Bu örnek Excel çalışma sayfaları ve hücreler için kasıtlı olarak sınırlıdır ve sınırlı biçimlendirme kullanır.

 Mümkün olduğunda, teknoloji yönetici kod tarafından açılmış .NET uzaktan iletişim kanalı kullanır `Communicator` bilgiler Excel işlemde çalışan içinde ayıklamak için sınıf.

## <a name="com-visibility"></a>COM görünürlüğü
 Bu sınıf ve her öğenin olduğuna dikkat edin genişletmek <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> tüm sınıf <xref:System.Runtime.InteropServices.ComVisibleAttribute> değerini `true` sınıfları COM'a görünür olduğundan emin olmak için

## <a name="technologyname-property"></a>TechnologyName özelliği
 Bu geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.TechnologyName%2A?displayProperty=fullName> özelliği, her bir bileşen uzantısı için temel alınan teknoloji tanımlayan benzersiz ve anlamlı bir ad belirtmelisiniz. Bu uzantı için "Excel" bir değerdir.

## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel Method
 Bu geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetControlSupportLevel%2A?displayProperty=fullName> yöntemi teknoloji Yöneticisi sağlanan tanıtıcı tarafından temsil edilen denetim için sunabileceğiniz destek düzeyini gösteren bir sayı döndürür. Döndürülen değer arttıkça daha fazla teknoloji Yöneticisi denetimi destekleyebilir. Bu durumda, yöntem denetimi içeren pencere denetler ve Excel çalışma ise, yöntem en yüksek değeri döndürür; Aksi takdirde, destek yok sağlanmadığını gösteren sıfır döndürür.

## <a name="methods-to-get-an-element"></a>Bir öğeyi almak için yöntemleri
 Kodlanmış UI test çerçevesi tarafından bir tanıtıcı ekran ya da farklı bir teknoloji öğeden noktasında sağlayarak bir öğe teknolojiye özgü almak için kullanılan birkaç önemli yöntem vardır. Bu yöntemler için kod değerleridir. Temel yöntemler aşağıdaki gibidir:

-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetFocusedElement%2A?displayProperty=fullName>

-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromPoint%2A?displayProperty=fullName>

-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromWindowHandle%2A?displayProperty=fullName>

-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromNativeElement%2A?displayProperty=fullName>

-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.ConvertToThisTechnology%2A?displayProperty=fullName>

## <a name="parsequeryid-method"></a>ParseQueryId yöntemi
 Kodlanmış UI testi oluşturduğunuzda, kullanıcı testinde bazı veya tüm denetimler için özellik değerlerini belirtebilirsiniz. Bu özellik değerlerini test çerçevesi tarafından test sırasında belirli kullanıcı Arabirimi denetimlerini bulmak için kullanılan arama özellikleri olarak adlandırılan ad-değer çiftleri oluşturmak için kullanılır. Tüm arama özellikleri birlikte değerini temsil eden <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A?displayProperty=fullName> her denetimi içeren teknolojisinde her öğesinin özelliği. Bir denetim, test sırasında birkaç kez bulunacak olabileceğinden, bu yöntem teknoloji Yöneticisi belirli bir denetim için arama özelliklerinin ayrıştırma en iyi duruma getirmek için bir yöntem sunar. Bu yöntem aynı zamanda framework sonraki aramalar için bu denetim için kullanabileceğiniz bir tanımlama bilgisi döndürür. Bu yöntemin kullanımı kullanan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> arama özelliklerini ayrıştırmak için yöntem.

## <a name="matchelement-method"></a>MatchElement yöntemi
 Teknoloji yöneticisi tarafından bir denetim araması gerçekleştirmek için uygulayabileceğiniz <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.Search%2A?displayProperty=fullName> olası eşleşmeler bir dizi döndürür veya throw yöntemi <xref:System.NotSupportedException>, kendi arama algoritması kullanılacak framework söyler. Her iki durumda da, uygulamanız gereken <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.MatchElement%2A> burada bu uygulama yeniden kullandığı bir yöntem <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> yöntemi.

## <a name="navigation-methods"></a>Gezinti yöntemleri
 Bu yöntemler üst, alt öğelerini veya eşdüzey sağlanan öğesinin UI hiyerarşisinden. , Basit ve açıkça açıklamalı kodudur.

## <a name="getexcelelement-internal-method"></a>GetExcelElement iç yöntemi
 İç bu yöntem bir pencere tanıtıcının ve Excel öğe hakkındaki bilgileri alır ve istenen Excel öğeyi döndürür.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager>
- <xref:System.NotSupportedException>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A>
- [Kodlanmış Kullanıcı Arabirimi Testlerini ve Eylem Kayıtlarını Microsoft Excel'i Desteklemek için Genişletme](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
