---
title: Birlikte çalışma derlemeleri kullanarak komut durumunu belirleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4989910fdec968a4a05e2459e6625ee2c15fd9a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128184"
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Birlikte çalışma derlemeleri kullanarak komut durumunu belirleme
Bir VSPackage ele alabilir komutları durumunu izlemek gerekir. Ortamı, VSPackage içinde işlenen komut ne zaman etkin veya devre dışı duruma belirleyemiyor. Bu ortam komutu durumları hakkında bilgilendirmek için VSPackage sorumluluğunda olan, örneğin, genel durumu gibi komutlar **Kes**, **kopya**, ve **Yapıştır**.  
  
## <a name="status-notification-sources"></a>Durum bildirim kaynakları  
 Ortam VSPackages komutları hakkında bilgi alır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> VSPackage'nın parçası olan yöntemini, <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. Ortam çağrıları <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> iki koşullarda VSPackage yöntemi:  
  
-   (Sağ tıklayarak) ana menü ya da bir bağlam menüsündeki bir kullanıcı oturum açtığında, ortamını yürüten <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> tüm durumlarına belirlemek için bu menüsündeki komutlar yöntemi.  
  
-   Ne zaman VSPackage ortamı geçerli kullanıcı arabirimi (UI) güncelleştirmesini ister. Bu gibi kullanıcı için görüntülenmekte olan komutları meydana **Kes**, **kopya**, ve **Yapıştır** standart araç çubuğundaki gruplandırma, duruma etkin ve devre dışı bağlamını ve kullanıcı eylemleri yanıt.  
  
 Birden çok VSPackages Kabuk barındıran olduğundan, komutu durumunu belirlemek için her VSPackage yoklamak için gerekli kabuğun performans edilemeyecek düşmesine neden. Bunun yerine, kullanıcı Arabiriminde değişikliği aynı anda değiştiğinde, VSPackage ortam etkin olarak bildirmelisiniz. Güncelleştirme bildirimi hakkında daha fazla bilgi için bkz: [kullanıcı arabirimini güncelleştirme](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Durum bildirim hatası  
 Komut durumu değişikliği ortamının bildirmek için VSPackage başarısızlığını UI tutarsız bir durumda yerleştirebilirsiniz. Menüsünü ve bağlam menüsünden komutlarınızı, araç çubuğunda kullanıcı tarafından yerleştirilebileceğinin olduğunu unutmayın. Bu nedenle, yalnızca bir menü veya bağlam menüsü açtığında kullanıcı arabirimini güncelleştirme yeterli değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Uygulama](../../extensibility/internals/command-implementation.md)