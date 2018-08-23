---
title: 'Nasıl yapılır: oluşturma bir. Vsct mevcut bir dosya. Ctc dosya | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, creating based on a .ctc file
ms.assetid: 700e80a4-c1e1-4178-af53-45e86dd2c08b
caps.latest.revision: 9
manager: douge
ms.openlocfilehash: 0d267e6046539001cbe454ab69867c02f0a606ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686503"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>Nasıl yapılır: oluşturma bir. Vsct mevcut bir dosya. Ctc dosyası
Varolan komut tablosu .ctc kaynak dosyasından bir XML tabanlı .vsct dosyası oluşturabilirsiniz. Bunu yaptığınızda yeni avantajlarından yararlanabilirsiniz XML tabanlı [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] komut tablosu (VSCT) derleyici biçimi.  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>Bir .ctc dosyasından .vsct dosyası oluşturmak için  
  
1.  Perl dil bir kopyasını edinin.  
  
2.  Perl betik ConvertCTCToVSCT.pl, tipik olarak bulunan bir kopyasını elde  *\<Visual Studio SDK'sını yükleme yolu >* \VisualStudioIntegration\Tools\bin klasör.  
  
3.  Dönüştürmek istediğiniz .ctc kaynak dosyasının bir kopyasını edinin.  
  
4.  Dosyaları aynı dizine koyun.  
  
5.  İçinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] komut istemi penceresinin, dizine gidin.  
  
6.  Tür  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     Burada PkgCmd.ctc .ctc dosyasının adını ve PkgCmd.vsct oluşturmak istediğiniz .vsct dosyası adıdır.  
  
     Bu yeni .vsct XML komut tablosu kaynak dosyası oluşturur. Diğer .vsct dosyası gibi dosya Vsct.exe, VSCT derleyici kullanarak derleyebilirsiniz.  
  
    > [!NOTE]
    >  XML açıklamaları'yeniden biçimlendirme .vsct dosyası okunabilirliğini artırabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: oluşturma bir. Vsct dosyası](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)