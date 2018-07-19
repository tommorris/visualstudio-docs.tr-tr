---
title: Intellicode sorular ve yanıtlar
ms.date: 07/12/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: 79e18778eae231d16cf32c0fa68bcb6f5564b09d
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079317"
---
# Visual Studio Intellicode SSS

Visual Studio Intellicode gösterdiğiniz ilgi için teşekkür ederiz! Bu kısa SSS Umarım etkinleştirmiş olabilirsiniz sorulara yanıt.

## SORU. Visual Studio Intellicode nedir?

Build 2018'e Microsoft Visual Studio Intellicode, yapay ZEKA kullanarak yazılım geliştirme geliştiren yeni bir özellik duyurdu. Intellicode geliştiriciler yardımcı olur ve güvenle kod takımlar, sorunları daha hızlı bulmak ve kod incelemeleri odaklanın.

Nasıl nasıl yazılım geliştirme işlemini aşağıdaki yollarla geliştirir Intellicode gösterilen erken bir görünümü:

- Bağlama duyarlı kod tamamlama sunar
- Geliştiriciler desenleri ve ekip stillerini uyması için size yol gösterir
- Catch zor kod sorunlarını bulur
- Kod incelemeleri açısından gerçekten önemli olan alanlara dikkat çekmek tarafından odaklanır.

Geliştiriciler bulabilir daha fazla bilgi ve oturum yukarı haber ve gelecekteki özel önizlemelere adresindeki [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## SORU. Ne yapmak, müşterilerin Visual Studio Intellicode olanak sağlıyor mu?

Visual Studio Intellicode, yapay zeka (AI) aracılığıyla yeni üretkenlik geliştirmeleri sunan bir özellikleri aralığıdır.

Geliştiriciler şunları yapabilir [Deneysel bir uzantı indirmek](https://go.microsoft.com/fwlink/?linkid=872707) Visual Studio 2017 sürüm 15.7 ve üzeri. Uzantı şu anda sağlar:

- Üyeleri alfabetik listesi yalnızca sunmak yerine kullanmak geliştirici için büyük olasılıkla doğru API tahmin eden yapay ZEKA destekli IntelliSense. Bu dinamik listesi sağlamak için geliştirici geçerli kod bağlamı ve desenleri kullanır.

- Kod stili ve biçimlendirme çıkarımı yardımcı olan kuralları tutmak kodunuzu tutarlı dinamik olarak oluşturarak bir [.editorconfig dosyasındaki](../create-portable-custom-editor-options.md) gelen, kodlama stillerini ve biçimlerini tanımlamak amacıyla kod. Bu kuralları otomatik stil sunmak Visual Studio izin ve biçim bazısı, belgeyi temizleyin.

Önümüzdeki aylarda uzantısı ile daha fazla özellik güncelleştireceğiz.

## SORU. Neden EditorConfig çıkarımı filename 1 önüne ekleyin?

Visual Studio genişletilebilirlik ilgili bilinen sorundan 1 neden olur. sağ tıklayıp seçerek oluşturduğunuzda .editorconfig dosya adına eklenecek **Ekle > Yeni öğe**. Bu şekilde adlı dosyaları Visual Studio'da editorconfig işlemcisi tarafından tanınmıyor. Bu sorun Visual Studio 2017 sürümünde 15,8 Preview 4 sabittir, ancak o zamana kadar 1'de kaldırarak getirebilirler **Yeni Öğe Ekle** iletişim.

## SORU. EditorConfig kuralları alma etkisi my - neden göremiyorum?
Birkaç Bu sorun oluşabilir yaygın nedenler şunlardır:

- 15,8 Preview 3 önce Visual Studio 2017 sürümlerinde, tüm kapatıp gerekecektir kuralları oluşturduğunuz EditorConfig dosyasındaki görmek için açık belgeler etkili olur. 3 sürüm 15,8 Önizleme'de bu sorun düzeltilmiştir.
- Biçimlendirme kuralları hiçbir zaman görünür **hata listesi** ya da kodunuzda "squiggles" olarak. Ancak, olabilirler yeni belgeyi Biçimlendir (Ctrl + K, Ctrl + D) uzantıyı kullanarak Visual Studio 2017 sürüm 15,8 sabit Preview 3 veya üzeri

## SORU. Belge stili kuralları my - neden çözdüğüne olmayan biçimlendirme?
Birkaç Bu sorun oluşabilir yaygın nedenler şunlardır:

- Visual Studio 2017 sürüm 15,8 kullanmıyor olabilirsiniz Preview 3 veya daha yüksek. Geçerli belge için ek kod temizleme işlemini gerçekleştirmek için genişletilmiş "Belgeyi Biçimlendir" komutunu kullanmak için bu sürümü gerekir.
- Stil düzeltmeler kabul değil. Genişletilmiş özellik sorunları kural tabanlı belgeyi Biçimlendir düzeltme özelliği yalnızca sorunlar sabit bir dizi kapsar. Hangi sorunların giderilen değiştirebilirsiniz **Araçlar-Seçenekler** altında **metin düzenleyicisi > C# > kod Stili > biçimlendirme > Genel > biçimi belge ayarları (Deneme)**. Varsayılan ayarları bazı stili kuralları'nı düzeltmemeyi dikkat edin. Bu kabul **Araçlar > Seçenekler**. "Örtük/açık tür tercihleri Uygula" stil kuralları kullanımı hakkındaki örneğin çalışacak `var`.

## SORU. Hangi EditorConfig kuralları, Visual Studio Intellicode çıkarımını?

Bu özellik şu anda Deneysel, kurallar kümesini desteklemiyoruz şekilde belirtilmiştir [kod stili ayarları başvurusu](../editorconfig-code-style-settings-reference.md) henüz.

Intellicode, şu anda aşağıdaki kurallar çıkarabilir:

Biçimlendirme kuralları:

-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_method_declaration_empty_parameter_list_parentheses
-   csharp_space_between_method_call_name_and_opening_parenthesis
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_call_empty_parameter_list_parentheses
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_parentheses
-   csharp_space_after_cast
-   csharp_space_after_colon_in_inheritance_clause
-   csharp_space_before_colon_in_inheritance_clause
-   csharp_space_around_binary_operators
-   csharp_indent_switch_labels
-   csharp_indent_case_contents
-   csharp_indent_case_contents_when_block
-   csharp_indent_labels
-   csharp_preserve_single_line_blocks
-   csharp_preserve_single_line_statements
-   csharp_new_line_before_open_brace
-   csharp_new_line_before_else
-   csharp_new_line_before_catch
-   csharp_new_line_before_finally
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_between_query_expression_clauses

Stil kuralları
-   csharp__new_line_before_catch
-   csharp_new_line_before_else
-   csharp_new_line_before_members_in_anonymous_types
-   csharp_new_line_before_members_in_object_initializers
-   csharp_new_line_before_finally_style
-   csharp_new_line_between_query_expression_clauses
-   csharp_prefer_braces_style
-   csharp_preferred_modifier_order_style
-   csharp_prefer_simple_default_expression
-   csharp_preserve_single_line_blocks
-   csharp_space_after_cast
-   csharp_space_after_keywords_in_control_flow_statements
-   csharp_space_between_method_call_parameter_list_parentheses
-   csharp_space_between_method_declaration_parameter_list_parentheses
-   csharp_space_between_parentheses
-   csharp_style_expression_bodied_accessors
-   csharp_style_expression_bodied_constructors
-   csharp_style_expression_bodied_indexers
-   csharp_style_expression_bodied_methods
-   csharp_style_expression_bodied_operators
-   csharp_style_expression_bodied_properties
-   csharp_style_inlined_variable_declaration
-   csharp_style_pattern_local_over_anonymous_function
-   csharp_style_pattern_matching_over_as_with_null_check
-   csharp_style_var_for_built_in_types
-   csharp_style_var_when_type_is_apparent
-   dotnet_sort_system_directives_first
-   dotnet_style_explicit_tuple_names
-   dotnet_style_object_initializer
-   dotnet_style_predefined_type_for_locals_parameters_members
-   dotnet_style_predefined_type_for_member_access
-   dotnet_style_prefer_inferred_anonymous_type_member_names
-   dotnet_style_qualification_for_event
-   dotnet_style_qualification_for_field
-   dotnet_style_qualification_for_method
-   dotnet_style_qualification_for_property
-   dotnet_style_require_accessibility_modifiers

## SORU. Visual Studio Intellicode uzantı yakında diğer özellikleri var mı?

Kullanılabilir oldukça herkese açık şekilde paylaşma heyecan duyuyoruz özellikleri sayısına etkin olarak çalışıyoruz. Oturum Haberler ve güncelleştirmeler sırasında döngünüzün [ https://aka.ms/intellicode ](https://aka.ms/intellicode) şu yeni özellikler kullanılabilir olduğunda öğrenmek için ilk olarak.

## S: ne "yapay ZEKA destekli IntelliSense Intellicode düzenli IntelliSense iyi tarafından desteklenen" yapar?

Intellicode ile basit bir alfabetik liste üyelerinin sunmak yerine kullanmak için bir geliştirici için en olası API düzeltmesi tamamlanma listesi önerir. Geliştiricinin geçerli kod bağlamı kullanır ve modellere 2000 yüksek kalite bağlı olarak, açık kaynak projeleri Github'da her bu dinamik listesi sağlamak için 100'den fazla yıldız ile. Sonuçları en olası ve en ilgili API çağrıları tahmin eden bir model oluşturur.

## S: ne kadar iyi Intellicode tamamlama önerileri misiniz?

Biz Intellicode'un önerileri dahili olarak Microsoft'ta bir süre kullanıyor ve öneriler faydalı olduğunu düşündüğünüz. Sonuç olarak, kavram nasıl içinde bu önerileri için kodunuzu yazarken faydalıdır olacaktır. Visual Studio vermenizi isteriz [Intellicode uzantısı](https://go.microsoft.com/fwlink/?linkid=872707) deneyin. Bize sizin için şekli bildiğiniz ve görüşlerinizi bize bildirin. Biz de modelimiz bizim önerileri çekme tabanlı eğiteceğiz ve model geliştikçe uzantısı güncelleştireceğiz.

> [!NOTE]
> Kullanıcı tanımlı kodunuzu hiçbiri toplanır. Soru bakın [gizlilik](#privacy).

## SORU. Intellicode geleceği nedir?

Yapay ZEKA ve diğer gelişmiş teknikleri kullanarak Geliştirici üretkenliğini artırmak için yol çeşitli araştırırken ediyoruz. Microsoft Build 2018, biz burada düşünüyoruz AI geliştiricilere yardımcı olmak, ancak bunu kullanabileceğiniz birçok senaryolardan bazıları erken bir görünümünü gösterdi daha fazla! Biz gösterilene, bu nedenle oturum Haberler ve güncelleştirmeler sırasında için denemeler geliştiricilerden öğrenme ilgilendiğimiz [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## SORU. Bunu nin ücreti ne kadardır?

Duyuru yok sahibiz şu anda fiyatlandırma ile ilgili.

## SORU. Intellicode kullanıma ne zaman sunulacaktır?

Intellicode'un yapay ZEKA destekli IntelliSense, şu anda, ilk deneysel Önizleme aşamasındadır. Deneysel uzantıyı güncelleştirmek devam ve ek özellikler gelecekte ekleyeceğiz. Son sürüm için zamanlama sahibiz ancak biz olası en iyi deneyimi sunabilmek geri bildirim geliştiricilerden bizim için çok önemli. Oturum Haberler ve güncelleştirmeler sırasında döngünüzün [ https://aka.ms/intellicode ](https://aka.ms/intellicode).

## SORU. Bu deneyim, yalnızca Visual Studio ve C# için kullanılabilir mi?

Bir C# kod temeli üzerinde Visual Studio 2017'deki Build 2018'e en deneyimi gösterildi. Ancak, Intellicode daha fazla dil ve araçları Visual Studio ailesindeki gelecekte genişletmeye umuyoruz.

## SORU. <a name="whynointellisense"/> Intellicode öneriler my düzenleme deneyimi, neler olduğunu - #c dilinde göremiyorum?

Intellicode önerileri standart Visual Studio IntelliSense Arabiriminde C# için görünür. Bu UI geçersiz kılma uzantıları listenin en üstünde görüntülenmesini Intellicode "yıldızlı" önerilerini engelleyin. Bunları kapatmak ve IntelliSense'ı yeniden deneyerek uzantıları bu davranış neden olup olmadığını doğrulayabilirsiniz.

Bu sorun, çözmezse, Lütfen Visual Studio aracılığıyla sorunu bildirin [sorun bildir](https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) özellik ve raporunuzdaki Intellicode bahsedebilirsiniz.

## SORU. Bu uzantı çalıştırmak Visual Studio'nun hangi sürümü gerekiyor mu?

Visual Studio 2017 sürüm 15.7 Önizleme 5 ve Visual Studio Intellicode uzantısıdır (tüm SKU'lar). "Bu uzantı yüklü ürünlerden herhangi birinde yüklenebilir değil." ile uzantısı durur yüklemesi yüklü gerekli en düşük sürüm yoksa.

## SORU. Bu deneyim yalnızca İngilizce olarak kullanılabilir mi?

Intellicode bugün Önizleme uzantısı olduğundan ve biz bu özellikler çok sayıda müşteriler için ne kadar faydalı olduğunu anlamak için. Intellicode önizlemeden alırken kesinlikle olarak size hangi yerel ayarı veya ilk ve nasıl paketlenmiştir, desteklemek için dili BİLDİRİMİNİZE dayalı olarak ele alacağız.

## <a name="privacy"/> S: gizlilik? Buluta kodum gönderdiğiniz? Hangi müşteri verilerini Microsoft'a gönderilir?

Geliştiriciler Visual Studio Intellicode Deneysel Önizleme uzantı olarak bugün deneyimi davetlidir. Uzantının amacı, geliştiricilerin Intellicode'un özellikleri test ve ürün ekibine geri bildirim sağlamak için etkinleştirmektir.

Biz, bazı anonim kullanım ve ürünün iyileştirilmesine yardımcı olmak için uzantı hata raporlama verilerini yakalayın. Hiçbir kullanıcı tarafından tanımlanan kod Microsoft'a gönderilmez, ancak Intellicode sonuçlarının kullanımınızla ilgili bilgileri toplarız. Veriler yalnızca açık kaynaklı ve .NET türleri ve Intellicode'un önerilen listesinden seçilen üyeleri içerir. Geliştiriciler iyileştirilmiş tanesi [Visual Studio Deneyimini Geliştirme Programı](../../ide/visual-studio-experience-improvement-program.md), hangi kapanmadan Intellicode uzantısı için veri toplamayı çok. Menü çubuğundan seçin **yardımcı** > **geri bildirim gönder** > **ayarları**. İçinde **Visual Studio Deneyimini Geliştirme Programı** iletişim kutusunda **Hayır, katılmak istemiyorum** seçip **Tamam**.

Intellicode uzantısı düzenli aralıklarla yeniden anonimleştirilmiştir bir anketi Geliştirici isteyebilir. Kullanıcılar, haber ve gelecekteki bir özel Önizleme için kaydolabilir, ancak şu anda Deneysel uzantıyı kullanmak için bunu yapmak için gerekli değildir.

Gelecek özellikleri kayıt gerektiren bir hizmete erişim gerektirebilir. Bu özelliklerin özel önizlemesine hazır olduğunuzda biz daha fazla ayrıntı yayınlayacaksınız.
