---
title: "Yetenek bayrakları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, capability flags
ms.assetid: a3f6071c-eac8-4bcd-8ffd-8d0a2d24a252
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ec5cedcec1d79cbc3a71410a1048f5014c8aa9e3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="capability-flags"></a>Yetenek bayrakları
SCC_CAP_*xxx* bayrakların kaynak denetim eklentisi özelliklerini göstermek için kullanılan bit bayrağı. SCC_EXCAP_*xxx* bayrakların tamsayı değerlerini çözümleyin ve genişletilmiş özellikler gösteriyor artımlı bayrakları.  
  
|Yetenek kodu|Değer|Açıklama|  
|---------------------|-----------|-----------------|  
|`SCC_CAP_REMOVE`|0x00000001L|Destekler [SccRemove](../extensibility/sccremove-function.md) ve komutu.|  
|`SCC_CAP_RENAME`|0x00000002L|Destekler [SccRename](../extensibility/sccrename-function.md) ve komutu.|  
|`SCC_CAP_DIFF`|0x00000004L|Destekler [SccDiff](../extensibility/sccdiff-function.md) ve komutu.|  
|`SCC_CAP_HISTORY`|0x00000008L|Destekler [SccHistory](../extensibility/scchistory-function.md) ve komutu.|  
|`SCC_CAP_PROPERTIES`|0x00000010L|Destekler [SccProperties](../extensibility/sccproperties-function.md) ve komutu.|  
|`SCC_CAP_RUNSCC`|0x00000020L|Destekler [SccRunScc](../extensibility/sccrunscc-function.md) ve komutu.|  
|`SCC_CAP_GETCOMMANDOPTIONS`|0x00000040L|Destekler [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) ve komutu.|  
|`SCC_CAP_QUERYINFO`|0x00000080L|Destekler [SccQueryInfo](../extensibility/sccqueryinfo-function.md) ve komutu.|  
|`SCC_CAP_GETEVENTS`|0x00000100L|Destekler [SccGetEvents](../extensibility/sccgetevents-function.md) ve komutu.|  
|`SCC_CAP_GETPROJPATH`|0x00000200L|Destekler [SccGetProjPath](../extensibility/sccgetprojpath-function.md) ve komutu.|  
|`SCC_CAP_ADDFROMSCC`|0x00000400L|Destekler [SccAddFromScc](../extensibility/sccaddfromscc-function.md) ve komutu.|  
|`SCC_CAP_COMMENTCHECKOUT`|0x00000800L|Açıklama üzerinde checkout destekler.|  
|`SCC_CAP_COMMENTCHECKIN`|0x00001000L|Açıklama üzerinde iade destekler.|  
|`SCC_CAP_COMMENTADD`|0x00002000L|Açıklama Ekle destekler.|  
|`SCC_CAP_COMMENTREMOVE`|0x00004000L|Bir yorum Kaldır destekler.|  
|`SCC_CAP_TEXTOUT`|0x00008000L|Metin bir IDE tarafından sağlanan çıkış işlevi yazar.|  
|`SCC_CAP_ADD_STORELATEST`|0x00200000L|Farkları içermeyen dosyaları depolamak destekler.|  
|`SCC_CAP_HISTORY_MULTFILE`|0x00400000L|Birden çok dosya geçmişi destekler.|  
|`SCC_CAP_IGNORECASE`|0x00800000L|Büyük küçük harf duyarsız dosya karşılaştırma destekler.|  
|`SCC_CAP_IGNORESPACE`|0x01000000L|Beyaz alan yoksayar karşılaştırma dosya destekler.|  
|`SCC_CAP_POPULATELIST`|0x02000000L|Ek dosyaları bulma destekler.|  
|`SCC_CAP_COMMENTPROJECT`|0x04000000L|Destekler yorumları projesi oluşturun.|  
|`SCC_CAP_DIFFALWAYS`|0x10000000L|Diff tüm durumlarda, denetimi altındaki destekler.|  
|`SCC_CAP_GET_NOUI`|0x20000000L|Eklenti bir kullanıcı Arabirimi için Get desteklemez ancak IDE hala çağrısı [SccGet](../extensibility/sccget-function.md).|  
|`SCC_CAP_REENTRANT`|0x40000000L|Desteklemeyeceğini ve iş parçacığı eklentidir. Sürüm 1.0, hiçbir eklentileri desteklemeyeceğini ve iş parçacığı açısından güvenli kabul edildiği. 1.1 eklentisi bu bitini konak paralel olarak birden çok proje açmak için izin verilir.|  
  
## <a name="capability-bits-added-in-version-12"></a>Yetenek BITS sürüm 1.2 eklendi  
  
|Yetenek kodu|Değer|Açıklama|  
|---------------------|-----------|-----------------|  
|`SCC_CAP_CREATESUBPROJECT`|0x00010000L|Destekler [SccCreateSubProject](../extensibility/scccreatesubproject-function.md).|  
|`SCC_CAP_GETPARENTPROJECT`|0x00020000L|Destekler [SccGetParentProjectPath](../extensibility/sccgetparentprojectpath-function.md).|  
|`SCC_CAP_BATCH`|0x00040000L|Destekler [SccBeginBatch](../extensibility/sccbeginbatch-function.md) ve [SccEndBatch](../extensibility/sccendbatch-function.md).|  
|`SCC_CAP_DIRECTORYSTATUS`|0x00080000L|Destekler [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md).|  
|`SCC_CAP_DIRECTORYDIFF`|0x00100000L|Destekler [SccDirDiff](../extensibility/sccdirdiff-function.md).|  
|`SCC_CAP_MULTICHECKOUT`|0x08000000L|Bir dosyada birden çok kullanıma destekler ve [SccIsMultiCheckoutEnabled](../extensibility/sccismulticheckoutenabled-function.md).|  
|`SCC_CAP_SCCFILE`|0x80000000L|MSSCCPRJ destekler. SCC dosya (tabi kullanıcı/yönetici geçersiz kılma) ve [SccWillCreateSccFile](../extensibility/sccwillcreatesccfile-function.md).|  
  
## <a name="capability-bits-added-in-version-13"></a>Yetenek BITS sürüm 1.3 eklendi  
 Bu bayrak için bir kerede geçirilir [SccGetExtendedCapabilities](../extensibility/sccgetextendedcapabilities-function.md) yeteneği desteklenip desteklenmediğini belirlemek için işlev.  
  
|Genişletilmiş özellik kodu|Değer|Açıklama|  
|------------------------------|-----------|-----------------|  
|`SCC_EXCAP_CHECKOUT_LOCALVER`|1.|Destekler `SCC_CHECKOUT_LOCALVER` kullanıma seçeneği.|  
|`SCC_EXCAP_BACKGROUND_GET`|2|Destekler [SccBackgroundGet](../extensibility/sccbackgroundget-function.md).|  
|`SCC_EXCAP_ENUM_CHANGED_FILES`|3|Destekler [SccEnumChangedFiles](../extensibility/sccenumchangedfiles-function.md).|  
|`SCC_EXCAP_POPULATELIST_DIR`|4|Ek dizinler bulma destekler.|  
|`SCC_EXCAP_QUERYCHANGES`|5|Dosya değişiklikleri numaralandırma destekler.|  
|`SCC_EXCAP_ADD_FILES_FROM_SCC`|6|Destekler [SccAddFilesFromSCC](../extensibility/sccaddfilesfromscc-function.md).|  
|`SCC_EXCAP_GET_USER_OPTIONS`|7|Destekler [SccGetUserOption](../extensibility/sccgetuseroption-function.md).|  
|`SCC_EXCAP_THREADSAFE_QUERY_INFO`|8|Birden çok iş parçacığı üzerinde SccQueryInfo çağrılmasını destekler.|  
|`SCC_EXCAP_REMOVE_DIR`|9|SccRemoveDir işlevi destekler.|  
|`SCC_EXCAP_DELETE_CHECKEDOUT`|10|Kullanıma dosyaları silebilirsiniz.|  
|`SCC_EXCAP_RENAME_CHECKEDOUT`|11|Kullanıma dosyaları yeniden adlandırabilirsiniz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)