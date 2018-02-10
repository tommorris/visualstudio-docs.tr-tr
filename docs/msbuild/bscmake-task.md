---
title: "BscMake görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 011ac0344326b7b45d266717c9bdc7d823d93140
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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
|**ÇıktıDosyası**|İsteğe bağlı **dize** parametresi.<br /><br /> Varsayılan çıkış dosyası adı geçersiz kılan bir dosya adını belirtir.<br /><br /> Daha fazla bilgi için bkz: **/o** seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**PreserveSBR**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, nonincremental yapı zorlar. .Bsc dosyası var ve kesilmiş gelen .sbr dosyaları engeller bağımsız olarak bir tam, nonincremental yapı oluşur.<br /><br /> Daha fazla bilgi için bkz:  **/n**  seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**Kaynakları**|İsteğe bağlı **ITaskItem []** parametresi.<br /><br /> Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.|  
|**SuppressStartupBanner**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için bkz: **/nologo** seçeneğini [BSCMAKE seçenekleri](/cpp/build/reference/bscmake-options).|  
|**TrackerLogDirectory**|İsteğe bağlı **dize** parametresi.<br /><br /> İzleyici günlük dizinini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)