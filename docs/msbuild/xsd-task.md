---
title: XSD görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77abc3b0d933be0e9677a4d89e0463a5fc7b4926
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="xsd-task"></a>XSD Görevi
Şema veya sınıf dosyaları oluşturan bir kaynaktan XML şema tanımı Aracı (XSD.exe'nin) sarmalar.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **XSD** görev.  
  
-   **AdditionalOptions**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Komut satırında belirtilen seçeneklerinin listesi. Örneğin, "*/option1 /option2 /option#*". Diğer tarafından temsil edilmez seçeneklerini belirtmek için bu parametreyi kullanın **XSD** görev parametresi.  
  
-   **GenerateFromSchema**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Belirtilen şemadan oluşturulan türlerini belirtir.  
  
     Her biri bir XSD seçeneğine karşılık gelir aşağıdaki değerlerden birini belirtin.  
  
    -   **sınıfları** -   **/sınıfları**  
  
    -   **veri kümesi** - **/dataset**  
  
-   **Dil**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan kod için kullanılacak programlama dilini belirtir.  
  
     Aralarından seçim **CS** (C varsayılan değer #,), **VB** (Visual Basic) veya **JS** (JScript). Ayrıca uygulayan bir sınıf için tam bir ad belirtin `System.CodeDom.Compiler.CodeDomProvider Class`.  
  
-   **Namespace**  
  
     İsteğe bağlı **dize** parametresi.  
  
     Oluşturulan türleri için çalışma zamanı ad alanını belirtir.  
  
-   **Kaynakları**  
  
     Gerekli `ITaskItem[]` parametresi.  
  
     Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.  
  
-   **SuppressStartupBanner**  
  
     İsteğe bağlı **Boolean** parametresi.  
  
     Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.  
  
-   **TrackerLogDirectory**  
  
     İsteğe bağlı **dize** parametresi.  
  
     İzleyici günlük dizinini belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)