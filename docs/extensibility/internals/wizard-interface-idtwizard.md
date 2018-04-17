---
title: Sihirbaz arabirimi (IDTWizard) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7ebb605ed61cc06ef70fde97f3d5831c6d5c4503
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="wizard-interface-idtwizard"></a>Sihirbaz arabirimi (IDTWizard)
Tümleşik geliştirme ortamını (IDE) kullanan <xref:EnvDTE.IDTWizard> sihirbazları ile iletişim kurmak için arabirim. Sihirbazlar, IDE içinde yüklü olması için bu arabirimi uygulamalıdır.  
  
 <xref:EnvDTE.IDTWizard.Execute%2A> Yöntemi ile ilişkili yalnızca yöntemidir <xref:EnvDTE.IDTWizard> arabirimi. Sihirbaz bu yöntemi uygulaması ve IDE arabirimde yöntemini çağırır. Aşağıdaki örnek, yönteminin imzası gösterilmektedir.  
  
```  
/* IDTWizard Method */  
STDMETHOD(Execute)(THIS_  
   /* [in] */ IDispatch *Application,  
   /* [in] */ long hwndOwner,  
   /* [in] */ SAFEARRAY * *ContextParams,  
   /* [in] */ SAFEARRAY * *CustomParams,  
   /* [out] [in] */ wizardResult *RetVal  
   );  
```  
  
 Başlangıç mekanizması her ikisi için benzer **yeni proje** ve **Yeni Öğe Ekle**sihirbazları. Ya da başlatmak için arama <xref:EnvDTE.IDTWizard> Dteinternal.h içinde tanımlanan arabirimi. Tek fark, içerik ve arabirim çağrıldığında arabirimine geçirilen özel parametreleri kümesidir.  
  
 Aşağıdaki bilgiler açıklanır <xref:EnvDTE.IDTWizard> sihirbazları çalışılacak uygulamalıdır arabirimi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. IDE çağrıları <xref:EnvDTE.IDTWizard.Execute%2A> aşağıdaki Geçirme Sihirbazı'nı yöntemi:  
  
-   DTE nesnesi  
  
     Otomasyon modelin kökü DTE nesnesidir.  
  
-   Kod kesimi gösterildiği gibi pencere iletişim kutusu için tanıtıcı `hwndOwner ([in] long)`.  
  
     Bu sihirbaz kullanır `hwndOwner` Sihirbazı iletişim kutusu için üst olarak.  
  
-   Bağlam parametreleri geçirilen arabirimine değişken SAFEARRAY için kod kesimi gösterildiği gibi `[in] SAFEARRAY (VARIANT)* ContextParams`.  
  
     Bağlam parametreleri başlatılmakta Sihirbazı türü için özel değerler dizisi ve proje geçerli durumunu içerir. IDE bağlam parametreleri sihirbaza geçirir. Daha fazla bilgi için bkz: [bağlam parametreleri](../../extensibility/internals/context-parameters.md).  
  
-   Özel Parametreler geçirilen arabirimine bir değişken SAFEARRAY için kod kesimi gösterildiği gibi `[in] SAFEARRAY (VARIANT)* CustomParams`.  
  
     Özel Parametreler kullanıcı tarafından tanımlanan parametre dizisi içerir. .Vsz dosyası özel parametreler IDE geçirir. Değerler tarafından belirlenir `Param=` deyimleri. Daha fazla bilgi için bkz: [özel parametreler](../../extensibility/internals/custom-parameters.md).  
  
-   Arabirim dönüş değerleri  
  
    ```  
    wizardResultSuccess = -1,  
    wizardResultFailure = 0  
    wizardResultCancel = 1  
    wizardResultBackout = 2  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlam parametreleri](../../extensibility/internals/context-parameters.md)   
 [Özel Parametreler](../../extensibility/internals/custom-parameters.md)   
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)