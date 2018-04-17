---
title: 'Nasıl yapılır: devre dışı bırakılmış VSTO eklentisinin yeniden etkinleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Warning.DisabledAddIn
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disabled add-ins
- add-ins [Office development in Visual Studio], disabled
- add-ins [Office development in Visual Studio], enabling
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 25344d23e0c9f1d6d237d008b0f6b18372490d04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-re-enable-a-vsto-add-in-that-has-been-disabled"></a>Nasıl Yapılır: Devre Dışı Bırakılmış VSTO Eklentisini Yeniden Etkinleştirme
  Microsoft Office uygulamaları VSTO beklenmedik bir şekilde davranan eklentileri devre dışı bırakabilirsiniz. Bir uygulama VSTO eklentinizi yüklemez hata ayıklamak çalıştığınızda, uygulama sabit devre dışı ya da yumuşak devre dışı bırakılmış VSTO eklentinizi olabilir.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="hard-disabled-vsto-add-ins"></a>Sabit işlevi devre dışı bırakılmış VSTO eklentileri  
 Bir VSTO eklenti uygulamanın beklenmedik şekilde kapanmasına neden olduğunda sabit devre dışı bırakma ortaya çıkabilir. Hata ayıklayıcıyı, ayrıca geliştirme bilgisayarınızda ortaya çıkabilir <xref:Microsoft.Office.Tools.AddIn.Startup> VSTO eklentinizi olay işleyicisini yürütülüyor.  
  
#### <a name="to-re-enable-a-vsto-add-in"></a>Bir VSTO eklentisini yeniden etkinleştirmek için  
  
1.  Uygulamayı tıklatın **dosya** sekmesi.  
  
2.  Tıklatın *ApplicationName* **seçenekleri** düğmesi.  
  
3.  Kategoriler bölmesinde **eklentileri**.  
  
4.  Ayrıntılar bölmesinde, VSTO eklenti göründüğünü doğrulayın **devre dışı uygulama eklentileri** listesi.  
  
     **Adı** sütun bütünleştirilmiş kodun adını belirtir ve **konumu** sütun uygulama bildirimi tam yolunu belirtir.  
  
5.  İçinde **Yönet** kutusunda, **devre dışı öğeler**ve ardından **Git**.  
  
6.  VSTO eklenti seçin ve tıklatın **etkinleştirmek**.  
  
7.  **Kapat**'ı tıklatın.  
  
## <a name="soft-disabled-vsto-add-ins"></a>Yazılım işlevi devre dışı bırakılmış VSTO eklentileri  
 Bir VSTO eklentisi uygulamanın beklenmedik şekilde kapanmasına neden olmaz ve bir hata üretir yumuşak devre dışı bırakma ortaya çıkabilir. Sırasında işlenmeyen bir özel durum oluşturursa Örneğin, bir uygulama yumuşak VSTO eklenti devre dışı bırakabilir <xref:Microsoft.Office.Tools.AddIn.Startup> olay işleyicisi yürütülüyor.  
  
> [!NOTE]  
>  Bir yazılım işlevi devre dışı bırakılmış VSTO eklentisini yeniden etkinleştirdiğinizde, uygulama hemen VSTO eklenti yüklemeye çalışır. Başlangıçta VSTO eklenti yumuşak devre dışı bırak uygulamaya neden olan sorunu sabit değil, uygulama yumuşak VSTO eklenti yeniden devre dışı bırakır.  
  
#### <a name="to-re-enable-an-vsto-add-in"></a>Bir VSTO eklenti yeniden etkinleştirmek için  
  
1.  Uygulamayı tıklatın **dosya** sekmesi.  
  
2.  Tıklatın *ApplicationName* **seçenekleri** düğmesi.  
  
3.  Kategoriler bölmesinde **eklentileri**.  
  
4.  Ayrıntılar bölmesinde, VSTO eklenti göründüğünü doğrulayın **etkin olmayan uygulama eklentileri** listesi.  
  
     **Adı** sütun bütünleştirilmiş kodun adını belirtir ve **konumu** sütun uygulama bildirimi tam yolunu belirtir.  
  
5.  İçinde **Yönet** kutusunda, **COM eklentileri**ve ardından **Git**.  
  
6.  İçinde **COM eklentileri** devre dışı bırakılmış VSTO eklenti yanındaki iletişim kutusunda, onay kutusunu seçin.  
  
7.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office projelerinde hata ayıklama](../vsto/debugging-office-projects.md)   
 [VSTO Eklentilerini Programlama](../vsto/programming-vsto-add-ins.md)  
  
  