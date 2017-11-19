---
title: "Otomasyon kodu için sağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa1c2fa5d0da738057e59cdac007c499a834bc0a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="providing-automation-for-code"></a>Otomasyon kodu için sağlama
Kodunuz için bir otomasyon modeli oluşturma gerekli değildir. Ortamı SDK'sı, bunu yapmak için bir örnek sağlamaz. Kod modelleri hakkında bilgi için bkz: <xref:EnvDTE.CodeModel> nesne.  
  
 Kod modeli uygulamak için iç veri yapısı tarafından belirlenir hiçbir arabirim uygulamalıdır. Nesneleri öğesinden türetilmelidir `IDispatch` sınıfı.  
  
 Genişlettiğinizde, nesneleri <xref:EnvDTE.CodeModel> ve <xref:EnvDTE.FileCodeModel>, kullanılabilir <xref:EnvDTE.Project> nesne ve şu şekilde görünür:  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 Uygulanacak seçebilirler yalnızca `CodeModel` veya `FileCodeModel` , dönüş nesnesindeki arabirim, `Project` ve <xref:EnvDTE.ProjectItem> nesneleri. Proje sisteminiz için uygun olan bu arabirimden herhangi bir işlevsellik sağlar.  
  
 Yöntemleri veya özellikleri gibi özellikleri eklemek istiyorsanız, kullanılabilir değil standart `CodeModel` ve `FileCodeModel` arabirimleri, standart devralır kendi arabirimi oluşturun. Son kullanıcılar için aranacak bilmesi proje sisteminizle belgelediğinizden emin olun. Standart arabirimini döndürür, ancak kullanıcı çağırabilirsiniz `QueryInterface` yöntemi veya cast bulunmasını biliniyorsa arabiriminiz için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon modeline genel bakış](../../extensibility/internals/automation-model-overview.md)