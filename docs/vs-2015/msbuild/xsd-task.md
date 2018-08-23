---
title: XSD görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.task.xsd
- VC.Project.VCXMLDataGeneratorTool.Namespace
- VC.Project.VCXMLDataGeneratorTool.GenerateFromSchema
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XSD task (MSBuild (Visual C++))
- MSBuild (Visual C++), XSD task
ms.assetid: 15c99f5c-7124-4bbc-bc03-70c7bcce8893
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f5a6bf91c6e9218593031ff15f2b31822ea5fa1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694608"
---
# <a name="xsd-task"></a>XSD Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [XSD görevi](https://docs.microsoft.com/visualstudio/msbuild/xsd-task).  
  
  
Bir kaynaktan şema ya da sınıf dosyaları oluşturur XML şema tanımı Aracı (XSD.exe'nin) sarmalar.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır **XSD** görev.  
  
-   **AdditionalOptions**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Komut satırında belirtilen seçeneklerin bir listesi. Örneğin, "*/option1 /option2 /option#*". Diğer tarafından temsil edilmez seçeneklerini belirtmek için bu parametreyi kullanın **XSD** görev parametresi.  
  
-   **GenerateFromSchema**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Belirtilen şemadan oluşturulan türler belirtir.  
  
     Her biri bir XSD seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **sınıflar** -   **/sınıfları**  
  
    -   **veri kümesi** -   **/DataSet**  
  
-   **Dil**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan kod için kullanılacak programlama dilini belirtir.  
  
     Aralarından seçim **CS** (C varsayılan değer olan #), **VB** (Visual Basic) veya **JS** (JScript). Ayrıca uygulayan bir sınıf için tam bir ad belirtin `System.CodeDom.Compiler.CodeDomProvider Class`.  
  
-   **Namespace**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan türleri için çalışma zamanı ad alanını belirtir.  
  
-   **Kaynakları**  
  
     Gerekli `ITaskItem[]` parametresi.  
  
     Tüketilen ve görevler tarafından yayılan MSBuild kaynak dosya öğeleri bir dizisi tanımlanmaktadır.  
  
-   **SuppressStartupBanner**  
  
     İsteğe bağlı **Boole** parametresi.  
  
     Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisinin görüntülenmesini engeller.  
  
-   **TrackerLogDirectory**  
  
     İsteğe bağlı **dize** parametresi.  
  
     İzleyici günlüğü dizini belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



