---
title: BscMake görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- vc.task.bscmake
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- BscMake task (MSBuild (Visual C++))
ms.assetid: bb98fc67-cad8-43a7-9598-60df6d734db2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5bdf1cc5370a126eb09a8af1fa05c25134bedf77
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="bscmake-task"></a>BscMake Görevi
> [!IMPORTANT]
>  bscmake artık Visual Studio IDE tarafından kullanılır. Visual Studio 2008'den beri gözatma bilgilerini otomatik olarak çözüm klasöründeki bir .sdf dosyasında depolanır.  
  
 Microsoft Gözat bilgileri bakım yardımcı programı aracını (bscmake.exe) sarmalar.  Bscmake.exe aracı derleme sırasında oluşturulan kaynak tarayıcısı dosyalarından (.sbr) gözatma bilgileri dosyası (.bsc) oluşturur. Kullanım **Nesne Tarayıcısı** .bsc dosyasını görüntülemek için. Daha fazla bilgi için bkz: [BSCMAKE başvurusu](/cpp/build/reference/bscmake-reference).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır **BscMake** görev. Çoğu görevi parametreleri bir komut satırı seçeneğine karşılık gelir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**AdditionalOptions**|İsteğe bağlı **dize** parametresi.<br /><br /> Komut satırında belirtilen seçeneklerinin listesi. Örneğin, "/*seçenek 1* /*Seçenek2* /*seçeneği #*". Diğer tarafından temsil edilmez seçeneklerini belirtmek için bu parametreyi kullanın **BscMake** görev parametresi.<br /><br /> Seçenekler, daha fazla bilgi için bkz: [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**OutputFile**|İsteğe bağlı **dize** parametresi.<br /><br /> Varsayılan çıkış dosyası adı geçersiz kılan bir dosya adını belirtir.<br /><br /> Daha fazla bilgi için bkz: **/o** seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**PreserveSBR**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, nonincremental yapı zorlar. .Bsc dosyası var ve kesilmiş gelen .sbr dosyaları engeller bağımsız olarak bir tam, nonincremental yapı oluşur.<br /><br /> Daha fazla bilgi için bkz: **/n** seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**Kaynakları**|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.|  
|**SuppressStartupBanner**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için bkz: **/nologo** seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**TrackerLogDirectory**|İsteğe bağlı **dize** parametresi.<br /><br /> İzleyici günlük dizinini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)