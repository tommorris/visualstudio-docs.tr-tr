---
title: "Dil sunucu Protokolü'ne genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a7d93c2-31ea-4bae-8b29-6988a567ddf2
caps.latest.revision: "1"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 269c19410207e47f233eadfa984a84a7c8445743
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="language-server-protocol"></a>Dil sunucusu Protokolü

## <a name="what-is-the-language-server-protocol"></a>Dil sunucusu protokolü nedir?

Düzenleme özellikleri destekleyen zengin ister kaynak kodu otomatik-tamamlamalar veya **Tanıma Git** programlama dilinde bir düzenleyici veya IDE geleneksel çok zor ve zaman alıcı için. Genellikle Düzenleyicisi veya IDE programlama dilinde (tarayıcı, bir Ayrıştırıcıyı, bir tür denetleyicisi, bir oluşturucu ve daha fazlasını) etki alanı modeli yazma gerektirir. Örneğin, Eclipse IDE Java'da yazılmış bu yana C/C++ Eclipse IDE'de için destek sağlar Eclipse CDT eklentisi Java'da yazılmış olmalıdır. Bu yaklaşım C# Visual Studio için Visual Studio Code TypeScript C/C++ etki alanı modelinde ve ayrı etki alanı modeli uygulama anlamına gelir.

Oluştururken dile özgü etki alanı modelleri de bir geliştirme aracında varolan dile özgü kitaplıkları yeniden kullanabilir, çok daha kolaydır. Ancak, bu kitaplıklar, genellikle programlama dili kendisini (C/C++ modelleri uygulanan Örneğin, iyi C/C++ etki alanı) uygulanır. C/C++ Kitaplık TypeScript içinde yazılmış bir düzenleyicisine tümleştirme teknik olarak olası ancak yapmak sabit.

### <a name="language-servers"></a>Dil sunucuları

Başka bir yaklaşım, kendi işleminde kitaplığı çalıştırın ve cihazı için işlemler arası iletişim kullanmaktır. İleri ve geri gönderilen iletileri bir iletişim kuralı oluşturur. Dil sunucusu Protokolü (LSP) bir geliştirme aracında ve bir dil sunucu işlemi arasında alınıp iletileri Standartlaştırma üründür. Dil sunucuları veya demons kullanarak yeni ya da yeni bir fikir değil. Düzenleyiciler VIM ister ve Emacs anlamsal otomatik tamamlama desteği sağlamak için bir süre Bunu yapmak için. Çeşitli araçları için dil özellikleri gösterme için yararlı bir çerçeve sağlamak ve tümleştirmeler bu tür kolaylaştırmak için LSP amacı oluştu.

Ortak bir protokolle sahip mevcut bir uygulamasına dilin etki alanı modelinin yeniden kullanarak en az fuss geliştirme aracıyla içine dil özellikleri programlama tümleştirme sağlar. Bir dil server arka uç, PHP, Python veya Java yazılmış ve LSP çeşitli araçları kolayca tümleştirilecek etmenizi sağlar. Protokol ortak bir soyutlama düzeyinde çalışır, böylece bir aracı temel etki alanı modeline özgü nüanslarını tam olarak anlamak zorunda kalmadan zengin dil hizmet sunabilir.

## <a name="how-work-on-the-lsp-started"></a>Başlatılan LSP üzerinde nasıl çalışır

LSP zaman içinde geliştirilen ve bugün bu sürüm 3.0. Bir dil sunucu kavramı tarafından OmniSharp C# için zengin düzenleme özellikleri sağlamanın çekilmiş olduğunda başlatıldı. Başlangıçta, OmniSharp bir JSON yükü ile kullanılan HTTP protokol ve de dahil olmak üzere birkaç düzenleyicileri tümleşik [Visual Studio Code](https://code.visualstudio.com).

Aynı anda Microsoft içeren bir sunucuda TypeScript dil, düzenleyiciler Emacs ve Sublime Text gibi TypeScript destekleme fikir çalışmaya başladı. Bu uygulamada bir düzenleyici stdin/stdout TypeScript server işlemine aracılığıyla iletişim kurar ve bir JSON yükü V8 hata ayıklayıcı protokolüyle esin istekleri ve yanıtları için kullanır. TypeScript sunucunun TypeScript Sublime eklentisi ve VS Code TypeScript zengin düzenleme için tümleştirilmiştir.

İki farklı dil sunucu tümleşik sonra, düzenleyiciler ve IDE için ortak bir dil sunucu protokol keşfetmek VS Code takım başlatıldı. Ortak bir protokolle farklı IDE tarafından kullanılabilecek tek bir dil sunucusunun oluşturmak bir dil sağlayıcısı sağlar. Bir dil sunucu tüketici protokolünün istemci tarafı anda uygulamak yalnızca içeriyor. Bu dil sağlayıcısı ve dil tüketici için win win durumda olur.

Daha fazla dil özellikleri VS kod dili API esin ile genişletmeden TypeScript sunucusu tarafından kullanılan protokol ile dil sunucusu protokolü başlatıldı. Protokol basitliği ve varolan kitaplıkları nedeniyle uzaktan çağrılması için JSON-RPC ile yedeklenir.

VS team örneklenmiş yanıt birkaç linter dil sunucuları uygulayarak Protokolü tüy (tarama) istekleri dosya kod ve algılanan uyarı ve hataların bir dizi döndürür. Hedef bir düzenleyici oturumu sırasında birçok linting istekleri olacağını anlamına gelir bir belgede kullanıcı düzenlemeleri olarak bir dosya için tüy oluştu. Bir sunucuyu ve yeni bir linting işlemi her kullanıcı düzenleme için başlatılması gerek çalıştıran tutmak için mantıklı hale. VS Code'nın da dahil olmak üzere birkaç linter sunucuya uygulanan ESLint ve TSLint uzantıları. Bu iki linter sunucu TypeScript/JavaScript uygulanan hem Node.js üzerinde çalıştırın. Bunlar protokolünün istemci ve sunucu parçası uygulayan bir kitaplık paylaşımı.

## <a name="how-the-lsp-works"></a>LSP nasıl çalışır?

Bir dil sunucusunun kendi işleminde çalışır ve araçları Visual Studio veya VS Code gibi JSON-RPC dil protokolünü kullanarak sunucusu ile iletişim. Adanmış bir işlemde çalışan dil sunucusu başka bir avantajı, tek bir işlem modeli ile ilgili performans sorunlarını kaçınılması ' dir. İstemci ve sunucu Node.js içinde yazılan gerçek taşıyıcı kanal ya da stdio, yuva, adlandırılmış kanallar veya düğüm IPC olabilir.

Aşağıda bir örnek nasıl yordamı sırasında bir aracı ve bir dil sunucusu iletişim kurmak için oturum düzenliyor:

![LSP Akış Diyagramı](media/lsp-flow-diagram.png)

* **Kullanıcı aracı (bir belge olarak adlandırılır) bir dosyayı açar**: aracı dil sunucunun bir belgenin açık olduğunu bildirir (' textDocument/didOpen'). Şu andan itibaren gerçekte belgesinin içeriğini hakkında artık dosya sisteminde değildir ancak bellekte aracı tarafından tutulur.

* **Kullanıcı düzenlemeleri yapar**: Belge değişikliği (' textDocument/didChange') sunucusu aracı konusunda sizi bilgilendirir ve programının anlamsal bilgilerin dil sunucu tarafından güncelleştirilir. Bu olduğu sürece, dil server bu bilgileri analizleri yaparken ve algılanan hataları ve Uyarıları (' textDocument/publishDiagnostics') aracıyla bildirir.

* **Kullanıcı bir simge Düzenleyicisi'nde hakkında "Tanıma Git" yürütür**: aracı iki parametreye sahip bir ' textDocument/tanımı' isteğini gönderir: (1) URI belge ve tanımı isteği Git sunucuya başlatıldığı gelen (2 metin konumu. Sunucu URI belge ve simgenin tanımının belgesinin içindeki konumu ile yanıt verir.

* **Kullanıcı (dosya) belgeyi kapatır**: aracından belgeyi artık bellek ve geçerli içeriğini şimdi şimdi dosya sisteminde güncel olan dil sunucusunun bildiren bir ' textDocument/didClose' bildirim gönderilir.

Bu örnek Protokolü "Tanıma Git", "Tüm başvuruları Bul" gibi Düzenleyicisi özellikleri düzeyinde dil sunucusu ile nasıl iletişim kurduğu gösterilmektedir. Protokolü tarafından kullanılan veri Düzenleyicisi veya IDE 'veri türleri' şu anda açık metin belgesi ve imleci konumunu gibi türleridir. Veri türleri, genellikle soyut söz dizimi ağaçları ve derleyici simgeler (örneğin, çözümlenen türleri, ad alanları,...) sağlayacak bir programlama dili etki alanı modeli düzeyinde değildir. Bu protokol önemli ölçüde basitleştirir.

Artık daha fazla ayrıntı ' textDocument/tanımı' istekte bakalım. İstemci aracında bir C++ belgesindeki "Tanıma Git" istek için dil sunucusu arasındaki Git yüklerini altındadır.

Bu istek.

```json
{
    "jsonrpc": "2.0",
    "id" : 1,
    "method": "textDocument/definition",
    "params": {
        "textDocument": {
            "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/use.cpp"
        },
        "position": {
            "line": 3,
            "character": 12
        }
    }
}
```

Bu yanıt verir:

```json
{
    "jsonrpc": "2.0",
    "id": "1",
    "result": {
        "uri": "file:///p%3A/mseng/VSCode/Playgrounds/cpp/provide.cpp",
        "range": {
            "start": {
                "line": 0,
                "character": 4
            },
            "end": {
                "line": 0,
                "character": 11
            }
        }
    }
}
```

Baktýðýmýzda, veri türleri düzenleyicisinin düzeyinde yerine programlama dili modeli düzeyini açıklayan dil sunucusu protokolü başarısını nedenlerle biridir. Bir metin belgesi URI standartlaştırmak çok kolaydır veya bir imleç konumu soyut söz dizimi ağaç ve derleyici simgeleri arasında farklı programlama dillerini Standartlaştırma ile karşılaştırılan.

Bir kullanıcı farklı dillerde çalışırken, VS Code her programlama dili için bir dil sunucusu genellikle başlatır. Aşağıdaki örnek, kullanıcının Java ve SASS dosyalar üzerinde çalıştığı bir oturumu gösterir.

![Java ve sass](media/lsp-java-and-sass.png)

### <a name="capabilities"></a>Özellikler

Her dil sunucu iletişim kuralı tarafından tanımlanan tüm özelliklerini destekler. Bu nedenle, istemci ve sunucu, 'Özellikler' aracılığıyla kendi desteklenen bir özellik kümesi sunar. Örnek olarak, ' textDocument/tanımı' isteği ele alabilir, ancak ' çalışma/simge' isteği işlemek olmayan bir sunucu olduğunu bildirir. Benzer şekilde, istemciler 'hakkında kaydetmek için ' sağlayabilir Duyurusu sunucu otomatik olarak düzenlenen belgeyi biçimlendirmek için metin düzenlemeleri hesaplayabilirsiniz böylece bir belge kaydetmeden önce bildirimleri.

## <a name="integrating-a-language-server"></a>Bir dil sunucusu tümleştirme

Belirli bir aracı gerçek tümleştirilmesi bir dil sunucusunun dil sunucusu protokolü tarafından tanımlı değil ve aracı implementors bırakılır. Bazı araçlar başlatabilir ve dil sunucusunun herhangi bir tür için konuşun bir uzantıya sahip olarak dil sunucuları genel tümleştirin. Uzantı bazı özel dil özellikleri sağlamak hala böylelikle diğer özel uzantı dil sunucu başına VS Code gibi oluşturun.

Dil sunucularını ve istemcilerini uyarlamasını basitleştirmek için kitaplıkları veya SDK istemcisi ve sunucusu bölümü vardır için. Bu kitaplıklar, farklı diller için sağlanır. Örneğin, bir [dil istemci npm modülünü](https://www.npmjs.com/package/vscode-languageclient) VS Code uzantısı ve başka bir dil sunucu tümleştirilmesi kolaylaştırmak için [dil sunucu npm modülünü](https://www.npmjs.com/package/vscode-languageserver) Node.js kullanarak bir dil sunucu yazmak için. Geçerli budur [listesi](https://github.com/Microsoft/language-server-protocol/wiki/Protocol-Implementations) destek kitaplıkların.

## <a name="using-the-language-server-protocol-in-visual-studio"></a>Visual Studio'da dil sunucusu protokolü kullanarak

* [Bir dil sunucusu Protokolü uzantısı ekleme](adding-an-lsp-extension.md) -Visual Studio'ya dil sunucusunun tümleştirme hakkında bilgi edinin.
