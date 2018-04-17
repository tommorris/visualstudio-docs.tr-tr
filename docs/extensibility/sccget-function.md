---
title: SccGet işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGet
helpviewer_keywords:
- SccGet function
ms.assetid: 09a18bd2-b788-411a-9da6-067d806e46f6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fb793eb5c35c4ca9ee22a58496ebe175b83c68e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sccget-function"></a>SccGet işlevi
Bu işlev, görüntüleme ve derleme ancak düzenlemek için bir veya daha fazla dosyalarının bir kopyasını alır. Çoğu sistemlerinde, dosyalar salt okunur olarak etiketlenir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SCCRTN SccGet(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 pvContext  
 [in] Kaynak Denetim eklentisi bağlam yapısı.  
  
 hWnd  
 [in] Kaynak Denetim eklentisi sağladığı tüm iletişim kutuları için üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 nFiles  
 [in] Belirtilen dosya sayısı `lpFileNames` dizi.  
  
 lpFileNames  
 [in] Alınacak dosyaların tam olarak nitelenmiş adlar dizisi.  
  
 fOptions  
 [in] Komut bayrakları (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).  
  
 pvOptions  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürmek için bu işlevi kaynak denetimi eklenti uyarlamasını beklenen:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Alma işlemi başarılı.|  
|SCC_E_FILENOTCONTROLLED|Dosya kaynak denetimi altında değil.|  
|SCC_E_OPNOTSUPPORTED|Kaynak Denetim sistem bu işlemi desteklemiyor.|  
|SCC_E_FILEISCHECKEDOUT|Kullanıcı şu anda kullanıma alınmış dosya alınamıyor.|  
|SCC_E_ACCESSFAILURE|Kaynak Denetim sistem ağ veya Çekişme sorun büyük olasılıkla erişilirken bir sorun oluştu. Yeniden deneme önerilir.|  
|SCC_E_NOSPECIFIEDVERSION|Belirtilen bir geçersiz sürüm veya tarih/saat.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata; Dosya eşitlenmedi.|  
|SCC_I_OPERATIONCANCELED|İşlem tamamlanmadan önce iptal edildi.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için yetkili değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir sayısı ve alınması için dosyaların adlarını dizisi ile çağrılır. IDE bayrağı geçerse `SCC_GET_ALL`, öğeleri buna `lpFileNames` dosyaları ancak dizinleri olup olmadığı ve alınmasına izin verilen dizinlerdeki kaynak denetimi altındaki tüm dosyaları olan.  
  
 `SCC_GET_ALL` Bayrağı ile birleştirilebilir `SCC_GET_RECURSIVE` belirli dizinlerdeki tüm dosyaları ve tüm alt dizinler de almak için bayrak.  
  
> [!NOTE]
>  `SCC_GET_RECURSIVE` hiçbir zaman olmadan iletilmesi gereken `SCC_GET_ALL`. Ayrıca, dizinleri C:\A ve C:\A\B üzerinde bir özyinelemeli geçirilen her ikisini de almak istiyorsanız C:\A\B ve onun tüm alt dizinler gerçekte iki kez alınır olduğunu unutmayın. IDE'nin sorumluluğundadır — ve kaynak denetim eklentinin — bu gibi çoğaltmaları dizi dışında tutulduğundan emin olmak için.  
  
 Son olarak, bir kaynak denetim olsa bile eklenti belirtilen `SCC_CAP_GET_NOUI` bayrağı belirten bir Get komutu için bir kullanıcı arabirimi yok, bu işlev hala dosyaları almak için IDE tarafından çağrılan başlatma. Bayrağı yalnızca IDE Get menü öğesi göstermez ve herhangi bir UI sağlamak eklenti olmadığını beklenen anlamına gelir.  
  
## <a name="renaming-and-sccget"></a>Yeniden adlandırma ve SccGet  
 Durum: bir kullanıcı dosyayı, örneğin,.txt, kullanıma ve değiştirdiği. .Txt denetlenebilir önce ikinci bir kullanıcı.txt kaynak denetimi veritabanında b.txt yeniden adlandırır, b.txt denetler, dosyaya bazı değişiklikleri yapar ve dosyayı denetler. İlk kullanıcı ilk kullanıcı için b.txt.txt dosyasının yerel kendi sürümünü yeniden adlandırır ve dosyanın get mu ikinci kullanıcı tarafından yapılan değişiklikleri istemektedir. Ancak, sürüm numaraları ve yerel önbellek hala.txt ilk sürümü yerel olarak depolanır ve bu nedenle kaynak denetimi farklar çözümlenemiyor düşünmektedir.  
  
 Kaynak denetimi sürümlerinin yerel önbelleği burada kaynak denetim veritabanı ile eşitlenmemiş hale bu sorunu çözmek için iki yolu vardır:  
  
1.  Kaynak denetim veritabanında şu anda kullanıma alınmış bir dosyayı yeniden adlandırma izin vermez.  
  
2.  "Eski Sil"tarafından yeni Ekle"ve ardından" denk yapın. Bunu yapmanın bir yolu algoritmasıdır.  
  
    1.  Çağrı [SccQueryChanges](../extensibility/sccquerychanges-function.md) işlevi b.txt kaynak denetimi veritabanında.txt, yeniden adlandırma hakkında bilgi edinin.  
  
    2.  Yerel.txt b.txt için yeniden adlandırın.  
  
    3.  Çağrı `SccGet` .txt ve b.txt işlevi.  
  
    4.  .Txt kaynak denetim veritabanında var olmadığından yerel sürüm önbelleğini eksik.txt sürüm bilgilerini temizlenir.  
  
    5.  Kullanıma alınmış b.txt dosyası yerel b.txt dosyasını içerikleriyle birleştirilir.  
  
    6.  Güncelleştirilmiş b.txt dosya artık denetlenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetim eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [Özel Komutlar Tarafından Kullanılan Bit Bayrakları](../extensibility/bitflags-used-by-specific-commands.md)