---
title: 'Nasıl yapılır: sembolleri kitaplığında belirleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Call Browser tool, identifying symbols in the library
- Call Browser tool
ms.assetid: 8fb0de61-71e7-42d1-8b41-2ad915474384
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 310ba421120101ce545888bcf4c069ca454cf086
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-identify-symbols-in-a-library"></a>Nasıl yapılır: sembolleri kitaplığında belirleme
Simgenin tarama araçları simgelerin hiyerarşik görünümleri görüntüler. Simgeleri ad alanları, nesneler, sınıflar, sınıf üyeleri ve diğer dil öğeleri temsil eder.  
  
 Hiyerarşideki her simge Sembol Kitaplığı tarafından geçirilen Gezinti bilgileri tanımlanabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nesnesi Yöneticisi aşağıdaki arabirimleri aracılığıyla:  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfoNode>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes>.  
  
 Hiyerarşideki simgenin konumunu bir simge ayırır. Belirli bir simgeye gitmek simgenin tarama araçları sağlar. Simgenin benzersiz, tam yolunu konumunu belirler. Her bir öğe yolu bir düğümdür. Yolun en üst düzey düğüm ile başlar ve belirli simgesiyle biter. Örneğin, M1 yöntemi C1 sınıfı bir üyesidir ve C1 N1 ad alanında ise, tam M1 yönteminin N1 yoludur. C1. M1. Bu yol üç düğümü içerir: N1, C1 ve M1.  
  
 Gezinti bilgileri sağlayan [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bulun, seçin ve korumak için Nesne Yöneticisi'ni seçili simgeleri hiyerarşi içinde. Bir tarama aracını diğerine gezinme sağlar. Kullanırken **Nesne Tarayıcısı** sembolleri göz atmak için bir [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] proje, bir yöntem sağ tıklatın ve Başlat **çağrısı tarayıcı** yöntemi çağrısı grafikte görüntülenecek aracı.  
  
 İki tür simgesi konumu açıklar. Kurallı biçimi tam yolun simgenin temel alır. Hiyerarşi benzersiz bir simgenin konumunu temsil eder. Simgenin tarama aracının bağımsızdır. Kurallı biçimi bilgilerini elde etmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nesnesi Yöneticisi çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> yöntemi. Sunu form belirli bir simgenin tarama aracı içinde simgenin konumunu açıklar. Simgenin konumunu hierarchicy diğer simgelerini konumda görelidir. Belirli bir sembol birkaç sunu yolları, ancak yalnızca bir kurallı yoluna sahip olabilir. Örneğin C1 sınıfı C2 sınıfından devralınır ve N1 ad alanında hem sınıflardır **Nesne Tarayıcısı** aşağıdaki hiyerarşik ağaç görüntüler:  
  
```  
N1  
    C1  
        Bases and Interfaces  
            C2  
    C2  
        Bases and Interfaces  
. . . . . . . . . . .  
  
```  
  
 Bu örnekte, C2 sınıfı kurallı yolunu N1 + C2 olur. C2 sunu yolunu C1 ve "Tabanları ve arabirimleri" düğümleri içerir: N1 C1 + "Tabanları ve arabirimleri" + C2.  
  
 Nesne Yöneticisi'ni çağrılarını sunu form bilgilerini elde etmek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> yöntemi.  
  
## <a name="identifying-a-symbol-in-the-hierarchy"></a>Hiyerarşideki bir simge tanımlama  
  
#### <a name="to-obtain-canonical-and-presentation-forms-information"></a>Kurallı elde edilir ve sunu bilgi formlar  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumCanonicalNodes%2A> yöntemi.  
  
     Nesne Yöneticisi'ni simgenin kurallı yolunda bulunan düğüm listesi elde etmek için bu yöntemi çağırır.  
  
    ```vb  
    Public Function EnumCanonicalNodes(ByRef ppEnum As Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes) As Integer  
        Dim EnumNavInfoNodes As CallBrowserEnumNavInfoNodes = _New CallBrowserEnumNavInfoNodes(m_strMethod)  
        ppEnum = CType(EnumNavInfoNodes, IVsEnumNavInfoNodes)  
        Return 0  
    End Function  
    ```  
  
    ```csharp  
    public int EnumCanonicalNodes(out Microsoft.VisualStudio.Shell.Interop.IVsEnumNavInfoNodes ppEnum)  
    {  
        CallBrowserEnumNavInfoNodes EnumNavInfoNodes =  
            new CallBrowserEnumNavInfoNodes(m_strMethod);  
        ppEnum = (IVsEnumNavInfoNodes)(EnumNavInfoNodes);  
        return 0;  
    }  
  
    ```  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsNavInfo.EnumPresentationNodes%2A> yöntemi.  
  
     Nesne Yöneticisi'ni simgenin sunu yolunda bulunan düğüm listesi elde etmek için bu yöntemi çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simgenin tarama araçları destekleme](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Nasıl yapılır: bir kitaplık nesnesi Yöneticisi ile kaydetme](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [Nasıl Yapılır: Kitaplık Tarafından Sağlanan Sembollerin Listelerini Nesne Yöneticisine Sunma](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)