---
title: 'Nasıl yapılır: betiğe ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- script debugging, attaching to script
- script, attaching to
- processes, attaching to script
- remote debugging, attaching to script
ms.assetid: 82013e9a-ef53-4fd2-b451-a6891cdc6307
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c38e965c5d424c7a3a6ffe4047e9422f1f9bb4f0
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
---
# <a name="how-to-attach-to-script"></a>Nasıl Yapılır: Betiğe Ekleme
Bu konuda, el ile Visual Studio hata ayıklayıcısı hata ayıklama için bir komut dosyası için nasıl ekleneceği açıklanmaktadır.  
  
### <a name="to-attach-to-a-running-process"></a>Bir çalışan işleme iliştirilemiyor  
  
1.  Üzerinde **hata ayıklama** menüsünde seçin **ekleme işlemi için**. (Proje açıksa seçin **ekleme işlemi için** üzerinde **Araçları** menü.)  
  
2.  İçinde **ekleme işlemi için** iletişim kutusu, göz **kullanılabilir işlemler** listesi ve bulma komut dosyasını işlemek istediğiniz eklemek. Komut dosyası işlemleri bakarak belirleyebilirsiniz **türü** sütun.  
  
    1.  Hata ayıklamak istediğiniz işlem başka bir bilgisayarda çalışıyorsa, uzak bilgisayarın seçmeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: bir uzak bilgisayar seçin](http://msdn.microsoft.com/en-us/4332ba8e-2f0b-4f62-b96a-e762b9f3c3ba).  
  
    2.  İşlemi farklı bir kullanıcı hesabı altında çalışıyorsa, seçin **işlemleri tüm kullanıcıları göster** onay kutusu.  
  
    3.  Aracılığıyla bağlandıysanız **Uzak Masaüstü Bağlantısı**seçin **tüm oturumları işlemleri göster** onay kutusu.  
  
3.  Eklemek istediğiniz işlemin'ı tıklatın.  
  
4.  İçinde **ekleme** kutusunda, görmeniz gerekir **kodu** veya **otomatik: betik kodu**. Başka bir şey görürseniz, aşağıdaki adımları izleyin:  
  
    1.  Tıklatın **seçin**.  
  
    2.  İçinde **kod türünü seç** iletişim kutusu, tıklatın **bu kodu türleri hata ayıklama** seçip **betik**.  
  
    3.  **Tamam**'ı tıklatın.  
  
5.  Tıklatın **Attach**.  
  
     Bu noktada, komut dosyasında hata ayıklama Internet Explorer'da devre dışı bırakıldığını belirten bir uyarı görebilirsiniz. Bu meydana gelirse, bkz: [Uyarı: betik hata ayıklamasını devre dışı](../debugger/warning-script-debugging-disabled.md).  
  
 **Kullanılabilir işlemler** listesi açtığınızda otomatik olarak görüntülenir **işlemleri** iletişim kutusu. İşlemleri başlatmak ve iletişim kutusu açıkken arka planda durdurun. Bu nedenle, içeriği her zaman güncel olmayabilir. Tuşlarına basarak işlemler geçerli listesini görmek için herhangi bir zamanda listesini yenileyebilirsiniz **yenileme** düğmesi.  
  
 Birden çok programlar ayıkladığınız ancak herhangi bir anda yalnızca bir program hata ayıklayıcısı'ndaki etkin olduğu durumlarda eklenebilir. Hata ayıklama konumu araç çubuğundaki etkin program ayarlayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: geçerli süreci Ayarla](http://msdn.microsoft.com/en-us/7e1d7fa5-0e40-44cf-8c41-d3dba31c969e).  
  
 Tüm **hata ayıklama** yürütme komutlarını etkin program etkiler. Herhangi bir hata ayıklaması programı işlemleri iletişim kutusundan bozulabilir. Bkz: [kesme noktalarını kullanma](../debugger/using-breakpoints.md).  
  
> [!NOTE]
>  Güvenilmeyen kullanıcı hesabı tarafından sahip olunan bir işlem ekleme çalışırsanız, bir güvenlik uyarısı iletişim onay görünür. Daha fazla bilgi için bkz: [güvenlik uyarısı: güvenilmeyen bir kullanıcıya ait bir işlem ekleme tehlikeli olabilir. Aşağıdaki bilgiler şüpheli görünüyorsa veya emin değilseniz, bu işlem için eklemeyin](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md).  
  
 Terminal Hizmetleri (Uzak Masaüstü) oturumunda ayıklarken bazı durumlarda, tüm kullanılabilir işlemler kullanılabilir işlemler listesinde görüntülenmez. Üzerinde [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] veya sonraki sürümleri, Visual Studio sınırlı bir kullanıcı olarak çalıştırıyorsanız, kullanılabilir işlemleri listesi gösterilmez Hizmetleri için kullanılan 0, oturumda çalışan işlemleri ve w3wp.exe dahil olmak üzere diğer sunucu işlemler. Visual Studio bir yönetici hesabı altında çalışan veya Terminal Hizmetleri oturumunda yerine server Konsolu Visual Studio çalıştırarak sorunu çözebilir. Bu geçici çözümler hiçbiri olası üçüncü seçenek vsjitdebugger.exe yazarak işleme iliştirilemiyor ise, Windows komut satırında -p ProcessId. İşlem kimliği tlist.exe kullanarak belirleyebilirsiniz. Tlist.exe elde etmek için karşıdan yükleyip Windows hata ayıklama araçları için kullanılabilir [Windows Donanım Geliştirici Merkezi](http://go.microsoft.com/fwlink/?linkid=1651).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İstemci tarafı komut dosyası hata ayıklama](../debugger/client-side-script-debugging.md)   
 [Çalıştırma işlemine iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Güvenlik Uyarısı: Güvenilmeyen bir kullanıcının sahip olduğu işleme ekleme tehlikeli olabilir. Aşağıdaki bilgiler şüpheli görünüyorsa veya emin değilseniz, bu işlem için eklemeyin](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)