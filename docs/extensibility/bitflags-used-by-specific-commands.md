---
title: Özel komutlar tarafından kullanılan bit işaretleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, bitflags used by specific commands
ms.assetid: 37969977-6f7d-45c9-ba03-1306ae71f5d1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3bc59c79e0f047cc7880332c4c23643ab2136c86
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108792"
---
# <a name="bitflags-used-by-specific-commands"></a>Özel komutlar tarafından kullanılan bit işaretleri
Kaynak Denetim eklentisi API işlevlerinde sayısı davranışını tek bir değer bir veya daha fazla BITS ayarlayarak değiştirilebilir. Bu değerleri bit işaretleri bilinir. Kaynak Denetim eklentisi API tarafından kullanılan çeşitli bit işaretleri, bunları kullanan bir işlev tarafından gruplandırılmış burada açıklanmıştır.  
  
## <a name="checked-out-flag"></a>Out bayrağı işaretli  
 Bu bayrak için ya da ayarlanabilir [SccAdd](../extensibility/sccadd-function.md) veya [SccCheckin](../extensibility/scccheckin-function.md).  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_KEEP_CHECKEDOUT`|0x1000|Dosya kullanıma tutun.|  
  
## <a name="add-flags"></a>Bayrakları ekleme  
 Bu bayrakların tarafından kullanılan [SccAdd](../extensibility/sccadd-function.md).  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_FILETYPE_AUTO`|0x00|Kaynak Denetim eklentisi otomatik olarak dosyanın metin veya ikili olup olmadığını algılamak için bekleniyor.|  
|`SCC_FILETYPE_TEXT`|0x01|Dosya türü metindir.|  
|`SCC_FILETYPE_BINARY`|0x04|İkili dosya türü olabilir. **Not:** `SCC_FILETYPE_TEXT` ve `SCC_FILETYPE_BINARY` bayrakları karşılıklı olarak birbirini dışlar.   Tam olarak bir ya da hiçbirini ayarlayın.|  
|`SCC_ADD_STORELATEST`|0x02|Yalnızca en son sürümünü (farkları yok) depolar.|  
  
## <a name="diff-flags"></a>Diff bayrakları  
 [SccDiff](../extensibility/sccdiff-function.md) Bu bayraklar fark işlemi kapsamını tanımlamak için kullanır. `SCC_DIFF_QD_xxx` Bayrakları karşılıklı olarak birbirini dışlar. Bunları herhangi biri belirtilmişse hiçbir görsel geribildirim, verilmesi alır. "Hızlı fark" içinde (QD) eklentisi nasıl yalnızca farklıysa, farklı bir dosyadır belirlemez. Hiçbiri "visual fark" yapılır bu bayraklar belirtilir; ayrıntılı dosya farkları hesaplanır ve görüntülenir. İstenen QD desteklenmiyorsa eklenti için en iyi bir sonraki taşır. Örneği için bir sağlama toplamı IDE ister ve eklenti bunu desteklemiyorsa, eklenti mu tam içeriğini (hala çok daha hızlı bir görüntü) denetleyin.  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_DIFF_IGNORECASE`|0x0002|Büyük/küçük farklar yoksay.|  
|`SCC_DIFF_IGNORESPACE`|0x0004|Boşluk farklılıklarını yoksay. **Not:** `SCC_DIFF_IGNORECASE` ve `SCC_DIFF_IGNORESPACE` bayrakların isteğe bağlı bit işaretleri.|  
|`SCC_DIFF_QD_CONTENTS`|0x0010|Tüm dosya içerikleri karşılaştırarak QD.|  
|`SCC_DIFF_QD_CHECKSUM`|0x0020|QD tarafından sağlama toplamı.|  
|`SCC_DIFF_QD_TIME`|0x0040|QD dosya tarih damgası tarafından.|  
|`SCC_DIFF_QUICK_DIFF`|0x0070|Bu, tüm QD bit işaretleri denetlemek için kullanılan bir maskesidir. Bir işlevdeki geçirilmemelidir; üç QD bit işaretleri karşılıklı olarak birbirini dışlar. QD her zaman UI görüntü anlamına gelir.|  
  
## <a name="populatelist-flag"></a>PopulateList bayrağı  
 Bu bayrak tarafından kullanılan [SccPopulateList](../extensibility/sccpopulatelist-function.md) içinde `fOptions` parametresi.  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_PL_DIR`|0x00000001L|IDE dizinleri, dosyaları değil geçiyor.|  
  
## <a name="populatedirlist-flags"></a>PopulateDirList bayrakları  
 Bu bayrakların tarafından kullanılan [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) içinde `fOptions` parametresi.  
  
|Seçenek değeri|Değer|Açıklama|  
|------------------|-----------|-----------------|  
|SCC_PDL_ONELEVEL|0x0000|Dizinlerin (varsayılan değer budur) dizinler için yalnızca bir düzey inceleyin.|  
|SCC_PDL_RECURSIVE|0x0001|Yinelemeli olarak verilen her dizini altındaki tüm dizinleri inceleyin.|  
|SCC_PDL_INCLUDEFILES|0x0002|Dosya adları İnceleme işleminde içerir.|  
  
## <a name="openproject-flags"></a>OpenProject bayrakları  
 Bu bayrakların tarafından kullanılan [SccOpenProject](../extensibility/sccopenproject-function.md) içinde `dwFlags` parametresi.  
  
|Seçenek değeri|Değer|Açıklama|  
|------------------|-----------|-----------------|  
|SCC_OP_CREATEIFNEW|0x00000001L|Proje kaynak denetiminde mevcut değilse oluşturun. Bu bayrak ayarlanmazsa, proje oluşturmak için kullanıcıya sor (sürece `SCC_OP_SILENTOPEN` bayrağı belirtilir).|  
|SCC_OP_SILENTOPEN|0x00000002L|Bir proje oluşturmak için kullanıcıya sorma; yalnızca dönüş `SCC_E_UNKNOWNPROJECT`.|  
  
## <a name="get-flags"></a>Bayrakları Al  
 Bu bayrakların tarafından kullanılan [SccGet](../extensibility/sccget-function.md) ve [SccCheckout](../extensibility/scccheckout-function.md).  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_GET_ALL`|0x00000001L|IDE dizinleri geçirme, olmayan dosyaları: tüm dosyalar bu dizinlerde alma.|  
|`SCC_GET_RECURSIVE`|0x00000002L|IDE dizinleri geçirme: Bu dizinler ve onların tüm alt dizinler alın.|  
  
## <a name="noption-values"></a>nOption değerleri  
 Bu bayrakların tarafından kullanılan [SccSetOption](../extensibility/sccsetoption-function.md) içinde `nOption` parametresi.  
  
|Bayrağı|Değer|Açıklama|  
|----------|-----------|-----------------|  
|`SCC_OPT_EVENTQUEUE`|0x00000001L|Olay sırası durumunu ayarlayın.|  
|`SCC_OPT_USERDATA`|0x00000002L|Kullanıcı verileri için belirtmek `SCC_OPT_NAMECHANGEPFN`.|  
|`SCC_OPT_HASCANCELMODE`|0x00000003L|IDE iptal işleyebilir|  
|`SCC_OPT_NAMECHANGEPFN`|0x00000004L|Ad değişikliği için bir geri çağırma ayarlayın.|  
|`SCC_OPT_SCCCHECKOUTONLY`|0x00000005L|Kaynak Denetim eklentisi UI checkout devre dışı bırakın ve çalışma dizinini ayarlı değil.|  
|`SCC_OPT_SHARESUBPROJ`|0x00000006L|Bir çalışma dizini belirtmek için kaynak denetimi sisteminden ekleyin. Doğrudan alt öğesi olması durumunda ilişkili projeye paylaşmak deneyin.|  
  
## <a name="dwval-bitflags"></a>dwVal bit işaretleri  
 Bu bayrakların tarafından kullanılan [SccSetOption](../extensibility/sccsetoption-function.md) içinde `dwVal` parametresi.  
  
|Bayrağı|Değer|Açıklama|Tarafından kullanılan `nOption` değeri|  
|----------|-----------|-----------------|-----------------------------|  
|`SCC_OPT_EQ_DISABLE`|0x00L|Olayı sırası etkinliği askıya alır.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_EQ_ENABLE`|0x01L|Olay sıra günlük kaydını etkinleştirir.|`SCC_OPT_EVENTQUEUE`|  
|`SCC_OPT_HCM_NO`|0 M|(Varsayılan) Hiçbir iptal modu vardır; Eklenti isterseniz sağlamanız gerekir.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_HCM_YES`|1 M|IDE iptal işler.|`SCC_OPT_HASCANCELMODE`|  
|`SCC_OPT_SCO_NO`|0 M|(Varsayılan) Eklenti kullanıcı Arabiriminden kullanıma için Tamam'ı tıklatın; Çalışma dizini ayarlanır.|`SCC_OPT_SCCCHECKOUTONLY`|  
|`SCC_OPT_SCO_YES`|1 M|Hiçbir eklenti UI checkout, çalışma dizini yok.|`SCC_OPT_SCCCHECKOUTONLY`|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)