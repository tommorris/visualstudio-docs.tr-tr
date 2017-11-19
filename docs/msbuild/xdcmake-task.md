---
title: "XDCMake görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.task.xdcmake
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- XDCMake task (MSBuild (Visual C++))
- MSBuild (Visual C++), XDCMake task
ms.assetid: a7de9c64-903a-4a02-85f3-f37672270f25
caps.latest.revision: "7"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 3d05dfce1679c6fba182c75a7d864cd09bc61b5b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="xdcmake-task"></a>XDCMake Görevi
XML Belge açıklama (.xdc) dosyaları bir .xml dosyasına birleştirir XML belgeleri Aracı (xdcmake.exe) sarmalar.  
  
 Bir .xdc dosyası kullanarak Visual C++ kaynak kodu ve derleme belge açıklamaları sağlama oluşturulduğunda [/doc](/cpp/build/reference/doc-process-documentation-comments-c-cpp) derleyici seçeneği. Daha fazla bilgi için bkz: [XDCMake başvurusu](/cpp/ide/xdcmake-reference), [XML belgesi oluşturma aracı özellik sayfaları](/cpp/ide/xml-document-generator-tool-property-pages)ve komut satırı Yardım seçeneği (**/?**) xdcmake.exe için.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, xdcmake.exe aracı birkaç komut satırı seçeneklerini destekler. Ek seçenekler belirttiğinizde desteklenir **/eski** komut satırı seçeneği.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **XDCMake** görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**AdditionalDocumentFile**|İsteğe bağlı **String []** parametresi.<br /><br /> Birleştirmek için bir veya daha fazla ek .xdc dosyalarını belirtir.<br /><br /> Daha fazla bilgi için bkz: **ek belge dosyaları** açıklamasında [XML belgesi oluşturma aracı özellik sayfaları](/cpp/ide/xml-document-generator-tool-property-pages). Ayrıca bkz. **/eski** ve **/Fs** xdcmake.exe için komut satırı seçenekleri.|  
|**AdditionalOptions**|İsteğe bağlı **dize** parametresi.<br /><br /> Komut satırında belirtilen seçeneklerinin listesi. Örneğin, "*/option1 /option2 /option#*". Diğer tarafından temsil edilmez seçeneklerini belirtmek için bu parametreyi kullanın **XDCMake** görev parametresi.<br /><br /> Daha fazla bilgi için bkz: [XDCMake başvurusu](/cpp/ide/xdcmake-reference), [XML belgesi oluşturma aracı özellik sayfaları](/cpp/ide/xml-document-generator-tool-property-pages)ve komut satırı Yardım (**/?**) xdcmake.exe için.|  
|**DocumentLibraryDependencies**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true` ve geçerli projenin bir statik kitaplık (.lib) projede çözümdeki bir bağımlılığa sahiptir, kitaplığı proje .xdc dosyaları geçerli proje için .xml dosyası çıkış eklenir.<br /><br /> Daha fazla bilgi için bkz: **belge kitaplığı bağımlılıkları** açıklamasında [XML belgesi oluşturma aracı özellik sayfaları](/cpp/ide/xml-document-generator-tool-property-pages).|  
|**ÇıktıDosyası**|İsteğe bağlı **dize** parametresi.<br /><br /> Varsayılan çıkış dosyası adı geçersiz kılar. Varsayılan adı işlenir ilk .xdc dosya adından türetilir.<br /><br /> Daha fazla bilgi için bkz: **/out:** `filename` seçeneğini [XDCMake başvurusu](/cpp/ide/xdcmake-reference). Ayrıca bkz. **/eski** ve **/Fo** xdcmake.exe için komut satırı seçenekleri.|  
|**ProjectName**|İsteğe bağlı **dize** parametresi.<br /><br /> Geçerli projenin adı.|  
|**SlashOld**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, ek xdcmake.exe seçeneklerini etkinleştirir.<br /><br /> Daha fazla bilgi için bkz: **/eski** xdcmake.exe için komut satırı seçeneği.|  
|**Kaynakları**|Gerekli `ITaskItem[]` parametresi.<br /><br /> Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.|  
|**SuppressStartupBanner**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için bkz: **/nologo** seçeneğini [XDCMake başvurusu](/cpp/ide/xdcmake-reference).|  
|**TrackerLogDirectory**|İsteğe bağlı **dize** parametresi.<br /><br /> İzleyici günlük dizinini belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)