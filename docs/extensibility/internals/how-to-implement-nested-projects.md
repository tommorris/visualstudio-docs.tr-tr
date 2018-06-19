---
title: 'Nasıl yapılır: iç içe geçmiş projeleri uygulamak | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing
- projects [Visual Studio SDK], nesting
ms.assetid: d20b8d6a-f0e0-4115-b3a3-edda893ae678
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dffef39d735b95cff01ead7087aa8b6286e39004
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33864468"
---
# <a name="how-to-implement-nested-projects"></a>Nasıl yapılır: iç içe Projeler uygulama

Oluşturduğunuzda bir iç içe proje türü vardır uygulanmalı birkaç bir ek adımlar şunlardır. Ana proje çözümü kendi iç içe geçmiş (alt) projeler için sahip aynı yükümlülüklerinizin bazıları alır. Ana proje projelerin bir çözüme benzer bir kapsayıcıdır. Özellikle, iç içe geçmiş projeleri hiyerarşisi oluşturmak için ana proje ve çözüm tarafından oluşturulması gereken birkaç olay vardır. Bu olaylar iç içe geçmiş projeleri oluşturmak için aşağıdaki işlemi açıklanmıştır.

## <a name="create-nested-projects"></a>İç içe geçmiş projeleri oluşturma

1.  Tümleşik geliştirme ortamı (IDE) çağırarak üst projenin proje dosyası ve başlangıç bilgileri yükler <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory> arabirimi. Ana proje oluşturulur ve çözüme eklendi.

    > [!NOTE]
    > Bu noktada, çünkü alt projeleri oluşturulmadan önce üst proje oluşturulmalıdır iç içe proje oluşturmak ana proje için işlemde çok erken. Bu dizisi aşağıdaki ana proje ayarları alt projelere uygulayabilirsiniz ve alt projeleri, gerekirse üst projelerinden bilgileri elde edebilirsiniz. Üzerinde kaynak kodu denetimi (SCC) ve Çözüm Gezgini gibi istemcileri tarafından gerekli değilse bu sırasıdır.

     Ana proje beklemelisiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> kendi iç içe geçmiş (alt) proje veya projeleri oluşturmadan önce IDE tarafından çağrılacak yöntem.

2.  IDE çağrıları `QueryInterface` için üst projede <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject>. Bu çağrı başarılı olursa, IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren%2A> iç içe proje ana proje için tüm açık üst yöntemi.

3.  Ana proje çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnBeforeOpeningChildren%2A> projeleri iç içe geçmiş dinleyicileri bildirmek için yöntemdir hakkında oluşturulacak. SCC, örneğin, çözüm ve proje oluşturma işleminde adımları sırayla ortaya çıkan öğrenmek için bu olayları dinler. Adımları bozuk meydana gelirse, çözümün kaynak kodu denetimi ile düzgün kaydettirilmemiş.

4.  Ana proje çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProject%2A> yöntemi veya <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.AddVirtualProjectEx%2A> her alt projeleri yöntemi.

     Geçirdiğiniz <xref:Microsoft.VisualStudio.Shell.Interop.__VSADDVPFLAGS> için `AddVirtualProject` yöntemi sanal (iç içe) proje yapıdan hariç proje penceresinde eklenmesi belirtmek için kaynak kodu denetimi ve benzeri eklendi. `VSADDVPFLAGS` iç içe proje görünürlüğünü denetleme ve hangi işlevleri onunla ilişkilendirilen belirtmek olanak sağlar.

     Bir proje üst projenin proje dosyası, ana proje çağrıları depolanan GUID içeren önceden var olan bir alt projeyi yeniden yüklediyseniz, `AddVirtualProjectEx`. Arasındaki tek fark `AddVirtualProject` ve `AddVirtualProjectEX` olan `AddVirtualProjectEX` belirtmek ana proje etkinleştirmek için bir parametreye sahip bir örneği başına `guidProjectID` etkinleştirmek alt projesi için <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfGuid%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.GetProjectOfProjref%2A> işlevi doğru.

     Varsa hiç GUID kullanılabilir, yeni bir iç içe proje eklediğinizde, çözüm bir proje için aynı anda oluşturur gibi üst eklenir. Bu proje GUID proje dosyasında kalıcı hale getirmek için ana proje sorumluluğundadır. İç içe proje silerseniz, bu proje için GUID da silinebilir.

5.  IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.OpenChildren> üst projenin her alt projede yöntemi.

     Ana proje uygulamalıdır `IVsParentProject` projeleri iç içe istiyorsanız. Ancak hiçbir zaman çağrıları proje üst `QueryInterface` için `IVsParentProject` üst projeleri altındaki olsa bile. Çözüm çağrısı işleme `IVsParentProject` ve uygulanmışsa, çağıran `OpenChildren` iç içe proje oluşturmak için. `AddVirtualProjectEX` her zaman çağrılır `OpenChildren`. Hiyerarşi oluşturma olayları sırayla tutmak için üst projesi tarafından hiçbir zaman çağrılmalıdır.

6.  IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A> alt projede yöntemi.

7.  Ana proje çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpeningChildren%2A> dinleyicileri üst alt projelerde oluşturulduğunu bildirmek için yöntem.

8.  IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents.FireOnAfterOpenProject%2A> tüm alt projeleri açtıktan sonra ana proje üzerinde yöntemi.

     Zaten yoksa üst projesini iç içe geçmiş her proje için bir GUID çağırarak oluşturur `CoCreateGuid`.

    > [!NOTE]
    > `CoCreateGuid` bir GUID oluşturulacak olduğunda bir COM API adı verilir. Daha fazla bilgi için bkz: `CoCreateGuid` ve GUID'lerini MSDN Kitaplığı'nda.

     Ana proje bu GUID IDE içinde açılmış bir sonraki başlatılışında alınması için kendi proje dosyasında depolar. 4. adım, arama için ilgili daha fazla bilgi için bkz: `AddVirtualProjectEX` almak için `guidProjectID` alt projesi için.

9. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> Üst öğe kimliği yöntemi çağrıldıktan sonra kurala göre içinde iç içe proje devretmenizi. <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> İçinde üst öğede çağrıldığında temsilci atamak istediğiniz bir proje katmandan düğüm özelliklerini alır.

     Üst ve alt projeleri program aracılığıyla örneği olduğundan iç içe proje özelliklerini bu noktada ayarlayabilirsiniz.

    > [!NOTE]
    > Yalnızca bağlam bilgilerini iç içe geçmiş projesinden aldığınız yapın, ancak, ana proje her bağlam için bu öğeyi olup olmadığını kontrol ederek sorabileceğiniz <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>. Bu şekilde, tek tek iç içe geçmiş projeler için fazladan dinamik Yardım öznitelikler ve özel menü seçenekleri ekleyebilirsiniz.

10. Hiyerarşi çağrısıyla Çözüm Gezgini'nde görüntülemek için yerleşik <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A> yöntemi.

     Hiyerarşi aracılığıyla ortamına geçirdiğiniz `GetNestedHierarchy` hiyerarşi için Çözüm Gezgini'nde görüntü oluşturmak için. Bu şekilde, çözüm proje var ve için yapı derleme Yöneticisi tarafından yönetilebilir veya kaynak kodu denetimi altında yerleştirilecek proje dosyalarında izin verebilir bilir.

11. Tüm iç içe geçmiş Project1 projelerde oluşturulduktan sonra Denetim geri çözüme geçirilir ve işlem Project2 için tekrarlanır.

     İç içe geçmiş projeleri oluşturmak için aynı bu işlem için bir alt öğesi olan bir alt projesi gerçekleşir. Bir alt Project1 olan, BuildProject1 alt projeleri varsa, bu durumda, bunların BuildProject1 sonra ve Project2 önce oluşturulması. Yinelemeli bir işlemdir ve hiyerarşi üstten aşağı yerleşik olarak bulunur.

     Ne zaman bir iç içe proje kapatıldığında kullanıcı çözümü veya özel Proje kendisi, başka bir yöntem üzerinde `IVsParentProject`, <xref:Microsoft.VisualStudio.Shell.Interop.IVsParentProject.CloseChildren%2A>, olarak adlandırılır. Ana proje çağrılarını sarmalar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.RemoveVirtualProject%2A> yöntemiyle <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeClosingChildren%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterClosingChildren%2A> iç içe geçmiş projeleri kapalı dinleyicileri çözüm olayları bildirmek için yöntemleri.

Aşağıdaki konular, iç içe geçmiş projeleri uyguladığınızda dikkate alınması gereken birkaç diğer kavramları Dağıt:

- [İç İçe Projeleri Kaldırma ve Yeniden Yükleme Konusunda Dikkat Edilmesi Gerekenler](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)
- [İç içe Projeler için Sihirbaz Desteği](../../extensibility/internals/wizard-support-for-nested-projects.md)
- [İç içe Projeler için Komut İşlemesi Uygulama](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)
- [İç içe Projeler için AddItem İletişim Kutusunu Filtreleme](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeni Öğe Ekleme İletişim Kutularına Öğe Ekleme](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Proje ve Öğe Şablonlarını Kaydetme](../../extensibility/internals/registering-project-and-item-templates.md)
- [Denetim Listesi: Yeni Proje Türleri Oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Bağlam Parametreleri](../../extensibility/internals/context-parameters.md)
- [Sihirbaz (.Vsz) Dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)