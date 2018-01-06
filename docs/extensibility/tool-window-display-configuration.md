---
title: "Araç penceresi ekran yapılandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, configuring
- tool windows, appearance
ms.assetid: 502a4926-bb83-473e-94e2-8e833c5f8b53
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 585ea78e0591ad979d09a3e5b208635c3f75f903
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="tool-window-display-configuration"></a>Araç penceresi ekran yapılandırması
Ne zaman bir VSPackage araç penceresi, varsayılan konumu, boyutu, yerleştirme stilini ve diğer görünürlük bilgileri kaydeder, isteğe bağlı değerleri belirtilir. Araç penceresi kayıt hakkında daha fazla bilgi için bkz: [kayıt defterinde araç pencereleri](../extensibility/tool-windows-in-the-registry.md)  
  
## <a name="window-display-information"></a>Pencere bilgilerini görüntüle  
 Bir aracı pencerenin temel görüntü yapılandırma en fazla altı isteğe bağlı değerlerde depolanır:  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              (Default)       = reg_sz: <Package GUID>Name            = reg_sz: <name of tool window>Float           = reg_sz: <position>Style           = reg_sz: <dock style>Window          = reg_sz: <window GUID>Orientation     = reg_sz: <orientation>DontForceCreate = reg_dword: 0x00000000  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|Ad|REG_SZ|"Kısa ad buraya"|Araç penceresi açıklayan kısa bir ad. Yalnızca kayıt defterinde referans için kullanılır.|  
|Kayan nokta|REG_SZ|"X1, Y1, X2, Y2"|Dört virgülle ayrılmış değerler. X1, Y1 olan aracı penceresinin sol üst köşesindeki koordinatı. X2, Y2 olduğu sağ alt köşedeki koordinatı. Ekran koordinatları olarak tüm değerlerdir.|  
|Stil|REG_SZ|"MDI"<br /><br /> "Float"<br /><br /> "Bağlı"<br /><br /> "Sekmeli"<br /><br /> "AlwaysFloat"|İlk belirten bir anahtar sözcük araç penceresi durumunu görüntüler.<br /><br /> "MDI" = ile MDI pencere yerleştirildi.<br /><br /> "Float" kayan =.<br /><br /> "Bağlı" = (penceresi girdisinde belirtilen) başka bir pencere ile bağlantılı.<br /><br /> "Sekmeli" = başka bir araç penceresi ile birlikte.<br /><br /> "AlwaysFloat" = yerleşik olamaz.<br /><br /> Daha fazla bilgi için aşağıdaki Açıklamalar bölümüne bakın.|  
|Pencere|REG_SZ|*\<GUID >*|Bir pencere için araç penceresi bağlı sekmeli veya GUID. GUID, kendi windows birini ya da windows biri ait olabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.|  
|Yönlendirme|REG_SZ|"Sol"<br /><br /> "Sağ"<br /><br /> "Top"<br /><br /> "Alt"|Aşağıdaki Açıklamalar bölümüne bakın.|  
|DontForceCreate|REG_DWORD|0 veya 1|Bu girdi varsa ve değeri sıfır olmadığında penceresi yüklendi ancak hemen görüntülenir.|  
  
### <a name="comments"></a>Açıklamalar  
 Yönlendirme girdi başlık çubuğunu tıklatıldığında burada araç penceresi noktalarını konumu tanımlar. Pencere girdisinde belirtilen pencere konumu görelidir. Stil Giriş "Bağlı" olarak ayarlanırsa, yönlendirme Giriş "Sol", "Sağ", "Üst" veya "Alt" olabilir. Stil Giriş "Sekmeli", "Girişi bırakılabilir" yönlendirme veya "Sağ" ve burada sekmesi eklenmiştir belirtiyorsa. Stil Giriş "Float" ise, araç penceresi ilk kayar. Başlık çubuğu tıklatıldığında, Yönlendirme ve pencere girişleri uygulamak ve penceresini "Sekmeli" stili kullanır. Stil Giriş "AlwaysFloat" ise, araç penceresi yerleşik olamaz. Stil Giriş "MDI" ise, araç penceresi MDI alanına bağlı ve pencere girdisi yok sayılır.  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {A0C5197D-0AC7-4B63-97CD-8872A789D233}\  
              (Default)       = reg_sz: {DA9FB551-C724-11D0-AE1F-00A0C90FFFC3}  
              DontForceCreate = reg_dword: 0x00000000  
              Float           = reg_sz: 100,100,450,300  
              Name            = reg_sz: Bookmarks  
              Orientation     = reg_sz: Left  
              Style           = reg_sz: Tabbed  
              Window          = reg_sz: {34E76E81-EE4A-11D0-00A0C90FFFC3}  
```  
  
## <a name="tool-window-visibility"></a>Araç penceresi görünürlüğü  
 İsteğe bağlı görünürlük alt anahtarda değerler aracı pencerenin görünürlüğü ayarları belirler. Değerlerin adları, pencerenin görünürlük gerektiren komutlar GUID'lerini depolamak için kullanılır. IDE komut yürütülürse, araç penceresi oluşturulur ve görünür hale güvence altına alır.  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        <Version>\  
          ToolWindows\  
            <Tool Window GUID>\  
              Visibility\  
                (Default) = reg_sz:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_dword:  
                <GUID>    = reg_sz:  
```  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|(Varsayılan)|REG_SZ|Yok.|Boş bırakın.|  
|*\<GUID >*|REG_DWORD veya REG_SZ|0 veya tanımlayıcı bir dize.|İsteğe bağlı. Girişin adı görünürlük gerektiren bir komut GUID olması gerekir. Değer, yalnızca bilgilendirici bir dize tutar. Genellikle, değeri olan bir `reg_dword` 0 olarak ayarlayın.|  
  
### <a name="example"></a>Örnek  
  
```  
HKEY_LOCAL_MACHINE\  
  Software\  
    Microsoft\  
      VisualStudio\  
        8.0Exp\  
          ToolWindows\  
            {EEFA5220-E298-11D0-8F78-00A0C9110057}\  
              Visibility\  
                (Default) = reg_sz:  
                {93694fa0-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
                {9DA22B82-6211-11d2-9561-00600818403B} = reg_dword: 0x00000000  
                {adfc4e66-0397-11d1-9f4e-00a0c911004f} = reg_dword: 0x00000000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage’lar](../extensibility/internals/vspackages.md)