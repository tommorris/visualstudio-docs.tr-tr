---
title: "Satırlar görünümü - örnekleme veri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Lines view
ms.assetid: 46497249-c797-42c5-a02c-3e4bb3b4ee60
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d08d090ad8e130e209af0d2057a065ed0bc474a7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lines-view---sampling-data"></a>Satırlar görünümü - örnekleme verileri
Veri örnekleme görünümünü örnekleri profil toplanan yükleyen yürütülmekte deyimleri için performans verilerini listeler satırları çalıştırın.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Bir kaynak dosyasında bir deyim bir kaynak dosyasında birden fazla satırı kapsayabilir ve tek bir satıra birden fazla deyim içerebilir. Bir deyim aşağıdaki tarafından tanımlanır:  
  
-   Function deyimi içeren kaynak dosyası.  
  
-   Deyimi içeren işlev.  
  
-   Kaynak satırı, deyim başlar.  
  
-   Deyim başlatan kaynak satırdaki karakter.  
  
-   Deyim erdiği kaynak satırı.  
  
-   Deyim erdiği kaynak satırdaki karakter.  
  
 Satır ad sütunu tanımlayıcısı verileri sıralanabilir bir birleşimini sağlar.  
  
 Tanımı gereği, diğer işlevleri bir deyim çağırmaz. Bu nedenle, yalnızca özel değerler listelenmektedir.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|İşlev satır içeren modülü adı.|  
|**Modül yolu**|İşlev satır içeren modülü yolu.|  
|**Kaynak dosya**|İşlev satır içeren kaynak dosyası.|  
|**İşlev adı**|İşlevin adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev başlangıç adresi.|  
|**Kaynak satırı başlangıç**|Bu örnek, toplanan kaynak dosyadaki başlangıç satır numarası.|  
|**Kaynak satır sonu**|Bu örnek, toplanan kaynak dosyasında bitiş satır numarası.|  
|**Kaynak karakter başlangıç**|Bu örnek, toplanan kaynak dosyası satırı başlangıç karakteri uzaklığı.|  
|**Kaynak karakter ucu**|Bu örnek, toplanan kaynak dosya satırında bir bitiş karakteri uzaklığı.|  
|**Satırı adı**|Aşağıdaki söz dizimini içeren satırı profil oluşturucu ürettiği tanıtıcısı:`Source File`**; [**  `Line Number Start` **,**`Character Start`**] ->; [** `Line Number End`**,**`Character End`**]**|  
|**Özel örnekleri**|İşlev satır yürütürken, toplanan örnek toplam sayısı.|  
|**Özel örnekleri %**|İşlev satır yürütürken, toplanan çalıştırmak profil tüm örneklerini yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satırlar görünümü - örnekleme](../profiling/lines-view-dotnet-memory-sampling-data.md)