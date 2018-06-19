---
title: Akıllı konak yardımcı arabirimleri uygulama | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Smart Host Helper Interfaces, implementing
ms.assetid: b9c44246-4d4d-469e-91be-00c8f5796fa5
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba571f6ad66855c44902e06467889e2cae5b4555
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792251"
---
# <a name="implementing-smart-host-helper-interfaces"></a>Akıllı Konak Yardımcı Arabirimleri Uygulama
[Idebugdocumenthelper arabirimi](../winscript/reference/idebugdocumenthelper-interface.md) arabirimi akıllı barındırmak için gereken birçok arabirimler için uygulamaları sağladığından etkin hata ayıklama için bir akıllı ana bilgisayar oluşturma görevini büyük ölçüde basitleştirir.  
  
 Kullanarak bir akıllı ana bilgisayar olacak şekilde `IDebugDocumentHelper`, bir ana bilgisayar uygulaması yalnızca üç şey yapmanız gerekir:  
  
1.  `CoCreate`İşlem Yöneticisi'ni hata ayıklama ve kullanım [Iprocessdebugmanager arabirimi](../winscript/reference/iprocessdebugmanager-interface.md) debuggable uygulamaların listesi uygulamanıza eklemek için arabirim.  
  
2.  Her komut dosyası için bir hata ayıklama belge Yardımcısı oluşturma nesnesi, kullanarak [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md) yöntemi. Belge adı, ana belge, metin ve komut dosyası blokları tanımlandığından emin olun.  
  
3.  Uygulama [Iactivescriptsitedebug arabirimi](../winscript/reference/iactivescriptsitedebug-interface.md) arabirimi uygulayan nesneniz üzerinde [Iactivescriptsite](../winscript/reference/iactivescriptsite.md) (Bu, etkin komut dosyası için gerekli olan) arabirimi. Yalnızca Önemsiz olmayan yöntemi `IActiveScriptSiteDebug` arabirimi yalnızca yardımcıya atar.  
  
 İsteğe bağlı olarak, konak uygulayabilirsiniz [Idebugdocumenthost arabirimi](../winscript/reference/idebugdocumenthost-interface.md) sözdizimi renk, belge bağlam oluşturma ve diğer genişletilmiş işlevselliği üzerinde ek denetim gerekiyorsa arabirim.  
  
 Akıllı ana bilgisayar Yardımcısı ana sınırlamasını içerikleri değiştirmek veya (belgeleri genişletebilirsiniz rağmen) eklenmiş sonra küçültme belgeleri yalnızca işleyebilir ' dir. Birçok akıllı ana bilgisayarlar için ancak sağladığı işlevleri tam olarak gerekenleri olur.  
  
 Aşağıdaki bölümlerde her adımın daha ayrıntılı açıklanmıştır.  
  
## <a name="create-an-application-object"></a>Uygulama nesnesi oluşturun  
 Akıllı ana bilgisayar Yardımcısı kullanılabilmesi için önce oluşturmak gerekli olan bir [Idebugapplication arabirimi](../winscript/reference/idebugapplication-interface.md) hata ayıklayıcı uygulamanızda temsil eden nesne.  
  
#### <a name="to-create-an-application-object"></a>Uygulama nesnesi oluşturmak için  
  
1.  İşlem hata ayıklama örneğini kullanarak Yöneticisi oluşturmak `CoCreateInstance`.  
  
2.  Çağrı [IProcessDebugManager::CreateApplication](../winscript/reference/iprocessdebugmanager-createapplication.md).  
  
3.  Kullanarak uygulamayı kümesinin adı [IDebugApplication::SetName](../winscript/reference/idebugapplication-setname.md).  
  
4.  Uygulama nesnesi kullanarak debuggable uygulamalar listesine eklemek [IProcessDebugManager::AddApplication](../winscript/reference/iprocessdebugmanager-addapplication.md).  
  
     Aşağıdaki kodu işlem özetlenmektedir, ancak hata denetimi veya diğer güçlü programlama tekniklerinin içermez.  
  
    ```  
    CoCreateInstance(CLSID_ProcessDebugManager, NULL,  
          CLSCTX_INPROC_SERVER | CLSCTX_INPROC_HANDLER  
          | CLSCTX_LOCAL_SERVER,  
    IID_IProcessDebugManager, (void **)&g_ppdm);  
    g_ppdm->CreateApplication(&g_pda);  
    g_pda->SetName(L"My cool application");  
    g_ppdm->AddApplication(g_pda, &g_dwAppCookie);  
    ```  
  
## <a name="using-idebugdocumenthelper"></a>Idebugdocumenthelper kullanma  
  
#### <a name="to-use-the-helper-minimal-sequence-of-steps"></a>Yardımcı (en az adımlar dizisi) kullanmak için  
  
1.  Her ana bilgisayar belge için kullanarak bir yardımcı oluşturmak, [IProcessDebugManager::CreateDebugDocumentHelper](../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md).  
  
2.  Çağrı [IDebugDocumentHelper::Init](../winscript/reference/idebugdocumenthelper-init.md) üzerinde Yardımcısı, ad, belge öznitelikleri ve benzeri vermiş.  
  
3.  Çağrı [IDebugDocumentHelper::Attach](../winscript/reference/idebugdocumenthelper-attach.md) belge (veya belge kökü ise NULL) için üst Yardımcısı ile ağacında belgenin konumunu tanımlamak ve hata ayıklayıcısı görünür yapmak için.  
  
4.  Çağrı [IDebugDocumentHelper::AddDBCSText](../winscript/reference/idebugdocumenthelper-adddbcstext.md) veya [IDebugDocumentHelper::AddUnicodeText](../winscript/reference/idebugdocumenthelper-addunicodetext.md) belgenin metni tanımlamak için. (Belge artımlı olarak, bir tarayıcı durumda olduğu gibi indirdiyseniz, bunlar birden çok kez çağrılabilir.)  
  
5.  Çağrı [IDebugDocumentHelper::DefineScriptBlock](../winscript/reference/idebugdocumenthelper-definescriptblock.md) her betik bloğu ve ilişkili komut dosyası motorları aralıklarını tanımlamak için.  
  
## <a name="implementing-iactivescriptsitedebug"></a>Iactivescriptsitedebug uygulama  
 Uygulanacak [IActiveScriptSiteDebug::GetDocumentContextFromPosition](../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)belirtilen siteye karşılık gelen Yardımcısı almak ve belirtilen kaynak bağlamının şu şekilde uzaklığı Başlangıç Belge alın:  
  
```  
pddh->GetScriptBlockInfo(dwSourceContext, NULL, &ulStartPos, NULL);  
```  
  
 Ardından, belirli bir karakter uzaklığı için yeni bir belge bağlamı oluşturmak için yardımcıyı kullanın:  
  
```  
pddh->CreateDebugDocumentContext(ulStartPos + uCharacterOffset, cChars, &pddcNew);  
```  
  
 Uygulanacak [IActiveScriptSiteDebug::GetRootApplicationNode](../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md), yalnızca çağrısı `IDebugApplication::GetRootNode` (devralınan [IRemoteDebugApplication::GetRootNode](../winscript/reference/iremotedebugapplication-getrootnode.md)).  
  
 Uygulanacak [IDebugDocumentHelper::GetDebugApplicationNode](../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md), yalnızca dönüş `IDebugApplication` başlangıçta işlem hata ayıklama Yöneticisi'ni kullanarak oluşturduğunuz.  
  
## <a name="the-optional-idebugdocumenthost-interface"></a>İsteğe bağlı Idebugdocumenthost arabirimi  
 Ana bilgisayar uygulaması sağlayabilir [Idebugdocumenthost arabirimi](../winscript/reference/idebugdocumenthost-interface.md) kullanarak [IDebugDocumentHelper::SetDebugDocumentHost](../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md) yardımcı üzerinde ek denetim vermek için. Konak arabirimi yapmanıza olanak sağlayan anahtar şeylerden bazıları şunlardır:  
  
-   Metin ekleme [IDebugDocumentHelper::AddDeferredText](../winscript/reference/idebugdocumenthelper-adddeferredtext.md) böylece konak karakterlerini hemen sağlamanız gerekmez. Karakterleri gerçekten gerekli olduğunda, yardımcı çağıracak [IDebugDocumentHost::GetDeferredText](../winscript/reference/idebugdocumenthost-getdeferredtext.md) ana bilgisayarda.  
  
-   Yardımcısı tarafından sağlanan varsayılan sözdizimi renklendirmesi geçersiz kılar. Yardımcı çağrıları [IDebugDocumentHost::GetScriptTextAttributes](../winscript/reference/idebugdocumenthost-getscripttextattributes.md) kendi varsayılan uygulama ana bilgisayar dönerseniz geri dönmeden karakter aralığı renklendirme belirlemek için `E_NOTIMPL`.  
  
-   Denetleme bilinmeyen uygulayarak Yardımcısı tarafından oluşturulan belge bağlamları sağlamak [IDebugDocumentHost::OnCreateDocumentContext](../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md). Bu, varsayılan belge bağlamı uygulama işlevselliğini geçersiz kılmak için ana sağlar.  
  
-   Bir yol adı ve belge için dosya sistemini de sağlar. Bazı hata ayıklama Uı'lar düzenlemek ve belgeye değişiklikleri kaydetmek için kullanıcının izin vermek için bunu kullanın. [IDebugDocumentHost::NotifyChanged](../winscript/reference/idebugdocumenthost-notifychanged.md) Belge kaydedildikten sonra konak bildirmek için çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkin komut dosyası hata ayıklamaya genel bakış](../winscript/active-script-debugging-overview.md)