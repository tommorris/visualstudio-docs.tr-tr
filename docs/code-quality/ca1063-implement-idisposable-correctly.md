---
title: "CA1063: IDisposable'ı doğru uygulayın"
ms.date: 02/12/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9205c20730681969550c3a2368e6ec889056648b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: IDisposable'ı doğru uygulayın

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep

`IDisposable` doğru uygulanmadı. Bu sorun için bazı nedenler aşağıda listelenmiştir:

- IDisposable sınıfında yeniden uygulanmış olur.

- Sonlandırma yeniden geçersiz kılınır.

- Dispose geçersiz kılınır.

- Dispose() ortak değil korumalı veya Dispose adlı.

- Dispose(bool) korumalı, sanal veya korumasız değil.

- Korumasız türlerinde Dispose() Dispose(true) çağırmanız gerekir.

- Korumasız türleri için her ikisi de Dispose(bool) veya servis talebi sınıfı sonlandırıcıyı Finalize uygulama çağırmaz.

Bu düzenleri herhangi birinin ihlali bu uyarı tetikler.

Bildirir ve IDisposable arabirimini uygulayan her korumasız türü kendi korumalı sanal void Dispose(bool) yöntem sağlamanız gerekir. Dispose() Dipose(true) çağırmalıdır ve Finalize Dispose(false) çağırmalıdır. Bildirir ve IDisposable arabirimini uygulayan bir korumasız türü oluşturuyorsanız, Dispose(bool) tanımlayın ve adlandırın. Daha fazla bilgi için bkz: [yönetilmeyen kaynakları Temizleme](/dotnet/standard/garbage-collection/unmanaged) içinde [.NET Framework tasarım yönergeleri](/dotnet/standard/design-guidelines/index).

## <a name="rule-description"></a>Kural açıklaması

Tüm IDisposable türleri Dispose kalıbını doğru uygulamalıdır.

## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl

Kodunuzu inceleyebilir ve aşağıdaki çözümlerden hangisinin bu ihlali düzeltilecek belirleyebilirsiniz.

- IDisposable {0} tarafından uygulanan ve temel sınıfın Dispose uygulama yerine geçersiz kılma arabirimleri listesinden kaldırın.

- Sonlandırıcıyı türünden {0} kaldırın (bool atma) Dispose geçersiz kılmak ve 'atma' yanlış olduğu bir kod yolunda sonlandırma mantığı yerleştirin.

- {0} kaldırın (bool atma) Dispose geçersiz kılmak ve 'atma' doğru olduğu bir kod yolunda dispose mantığı yerleştirin.

- Bu {0} ortak ve korumalı olarak bildirilmiş emin olun.

- {0} 'Dispose' olarak yeniden adlandırın ve onu olarak ortak ve korumalı bildirildiğinden emin olun.

- Bu {0} korumalı olarak bildirilmiş emin, sanal ve korumasız hale getirir.

- Dispose(true) çağırır sonra GC çağırır {0} değiştirin. Geçerli nesne örneği üzerinde SuppressFinalize ('this' veya 'Me' [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ve ardından döndürür.

- Böylece Dispose(false) çağırır ve ardından döndürür {0} değiştirin.

- Bildirir ve IDisposable arabirimini uygulayan bir korumasız türü oluşturuyorsanız, IDisposable uygulanması bu bölümde daha önce açıklanan deseni izler emin olun.

## <a name="when-to-suppress-warnings"></a>Ne zaman uyarıları bastırma

Bu kuraldan uyarıyı bastırmayın.

## <a name="pseudo-code-example"></a>Sözde kod örneği

Aşağıdaki sözde kodu Dispose(bool) yönetilen kullanan bir sınıfta nasıl uygulanması gerekir ve yerel kaynakların genel bir örnek sağlar.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources itself, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```