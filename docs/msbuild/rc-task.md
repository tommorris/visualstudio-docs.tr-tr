---
title: "RC görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- vc.task.rc
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- RC task (MSBuild (Visual C++))
- MSBuild (Visual C++), RC task
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 73e4544ab00142929bbd8d8dbdb154355c48c609
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="rc-task"></a>RC Görevi
Microsoft Windows Kaynak Derleyicisi aracı sarmalar rc.exe. **RC** görev imleçler, simgeler, bit eşlemler, iletişim kutuları ve yazı tipleri gibi kaynaklar bir kaynak (.res) dosyasına derler. Daha fazla bilgi için "Kaynak derleyicisi" bakın [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) Web sitesi.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda RCtask parametreler açıklanmaktadır. Çoğu görevi parametreleri ve parametreleri, birkaç kümelerini bir komut satırı seçeneğine karşılık gelir.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|**AdditionalIncludeDirectories**|İsteğe bağlı **String []** parametresi.<br /><br /> Bir dizin için dosyaları Ekle aranır dizinlerin listesi ekler.<br /><br /> Daha fazla bilgi için bkz: **/I** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**AdditionalOptions**|İsteğe bağlı **dize** parametresi.<br /><br /> Komut satırı optionsor örnek listesini **"***/option1 /option2 /option#*". Diğer tarafından temsil edilmez komut satırı seçeneklerini belirtmek için bu parametreyi kullanın **RC** görev parametresi.<br /><br /> Seçenekler, daha fazla bilgi için bkz: [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**Kültür**|İsteğe bağlı **dize** parametresi.<br /><br /> Kaynakları kullanılan kültür temsil eden bir yerel ayar Kimliğini belirtir.<br /><br /> Daha fazla bilgi için bkz: **/l** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**IgnoreStandardIncludePath**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, üst bilgi veya kaynak dosyaları için aradığında INCLUDE ortam değişkeni kontrol kaynak derleyicisi engeller.<br /><br /> Daha fazla bilgi için bkz: **/x** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**NullTerminateStrings**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, tüm dizelerini dize tablosunda null sonlandırır.<br /><br /> Daha fazla bilgi için bkz:  **/n**  seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**PreprocessorDefinitions**|İsteğe bağlı **String []** parametresi.<br /><br /> Kaynak derleyicisi bir veya daha fazla önişlemci simgelerini tanımlayın. Makro simgeleri listesini belirtin.<br /><br /> Daha fazla bilgi için bkz: **/d** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde. Ayrıca bkz. **UndefinePreprocessorDefinitions** bu tabloda.|  
|**ResourceOutputFileName**|İsteğe bağlı **dize** parametresi.<br /><br /> Kaynak dosyanın adını belirtir. Bir kaynak dosya adı belirtin.<br /><br /> Daha fazla bilgi için bkz: **/fo** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**ShowProgress**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, derleyici ilerlemesinde Raporu iletilerini görüntüler.<br /><br /> Daha fazla bilgi için bkz: **/v** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde.|  
|**Kaynak**|Gerekli `ITaskItem[]` parametresi.<br /><br /> Tüketilen ve görevler tarafından gösterilen MSBuild kaynak dosya öğeleri dizisi tanımlar.|  
|**SuppressStartupBanner**|İsteğe bağlı **Boolean** parametresi.<br /><br /> Varsa `true`, görev başladığında telif hakkı ve sürüm numarası iletisini görüntülenmesini engeller.<br /><br /> Daha fazla bilgi için türü **/?** komut satırı seçeneğini ve ardından bakın **/nologo** seçeneği.|  
|**TrackerLogDirectory**|İsteğe bağlı **dize** parametresi.<br /><br /> İzleyici günlük dizinini belirtir.|  
|**UndefinePreprocessorDefinitions**|Önişlemci bir simge tanımlarını Kaldır.<br /><br /> Daha fazla bilgi için bkz: **/u** seçeneğini [kullanarak RC (RC komut satırı)](http://go.microsoft.com/fwlink/?LinkId=155730) MSDN Web sitesinde. Ayrıca bkz. **PreprocessorDefinitions** bu tabloda.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)