---
title: XSD görevi | Microsoft Docs
ms.custom: ''
ms.date: 06/27/2018
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
ms.openlocfilehash: b292c0bf1bc80f811cbf2f845385f91987184674
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057378"
---
# <a name="xsd-task"></a>XSD Görevi
Şema veya sınıf dosyaları oluşturan bir kaynaktan XML şema tanımı Aracı (XSD.exe'nin) sarmalar.  

> [!NOTE]
> Visual Studio 2017 içinde C++ projesi XSD.exe'nin desteği kullanım dışıdır. Kullanmaya devam edebilirsiniz **Microsoft.VisualC.CppCodeProvider** el ile ekleyerek API'leri **CppCodeProvider.dll** GAC için. 
  
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