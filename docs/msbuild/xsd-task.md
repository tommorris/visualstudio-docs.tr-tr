---
title: XSD görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7505f3d18e0b32ebdbc8b82d447e49b26fe4182e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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