---
title: Yönetilen kod için temel doğruluk kuralları kural kümesi | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 631f0daf-1d42-4c90-a7dc-1a6a9de64c93
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4b435d813ad1e7c9308bfa6a7d8d243b877d6d6b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49184599"
---
# <a name="basic-correctness-rules-rule-set-for-managed-code"></a>Yönetilen kod için Temel Doğruluk Kuralları kural kümesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Temel doğruluk kuralları kural kümesi mantık hataları ve Framework API kullanımında yaygın hatalara odaklanır. Temel doğruluk kuralları, önerilen Minimum kurallar kural kümesine kurallar içerir. Daha fazla bilgi için [yönetilen kod için yönetilen önerilen kurallar kural kümesi](../code-quality/managed-recommended-rules-rule-set-for-managed-code.md) minimum kurallar rapor önerilen uyarıları listede genişletmek için bu kural içermelidir.  
  
 Aşağıdaki tabloda Microsoft temel doğruluk kuralları kural kümesindeki tüm kurallar açıklanmaktadır.  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1001](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Atılabilir alanlara sahip türler atılabilir olmalıdır|  
|[CA1009](../code-quality/ca1009-declare-event-handlers-correctly.md)|Olay işleyicilerini doğru bildirin|  
|[CA1016](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|Derlemeleri AssemblyVersionAttribute ile işaretleyin|  
|[CA1033](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır|  
|[CA1049](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|Yerel kaynaklara sahip türler atılabilir olmalıdır|  
|[CA1060](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|P/Invokes öğesini NativeMethods sınıfına taşıyın|  
|[CA1061](../code-quality/ca1061-do-not-hide-base-class-methods.md)|Taban sınıf yöntemlerini gizlemeyin|  
|[CA1063](../code-quality/ca1063-implement-idisposable-correctly.md)|IDisposable'ı doğru uygulayın|  
|[CA1065](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|Beklenmedik konumlarda özel durumlar harekete geçirmeyin|  
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|Yinelenen hızlandırıcılardan kaçının|  
|[CA1400](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)|P/Invoke giriş noktaları bulunmalıdır|  
|[CA1401](../code-quality/ca1401-p-invokes-should-not-be-visible.md)|P/Invoke'lar görünür olmamalıdır|  
|[CA1403](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)|Otomatik Yerleşim türleri COM görünebilir olmamalıdır|  
|[CA1404](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)|P/Invoke ardından hemen GetLastError çağırın|  
|[CA1405](../code-quality/ca1405-com-visible-type-base-types-should-be-com-visible.md)|COM görünebilir tür taban türler COM görünebilir olmalıdır|  
|[CA1410](../code-quality/ca1410-com-registration-methods-should-be-matched.md)|COM kayıt yöntemleri eşleşmelidir|  
|[CA1415](../code-quality/ca1415-declare-p-invokes-correctly.md)|P/Invoke'lar doğru bildirin|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|Boş Sonlandırıcıları kaldırın|  
|[CA1900](../code-quality/ca1900-value-type-fields-should-be-portable.md)|Değer tür alanları taşınabilir olmalıdır|  
|[CA1901](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|P/Invoke bildirimleri taşınabilir olmalıdır|  
|[CA2002](../code-quality/ca2002-do-not-lock-on-objects-with-weak-identity.md)|Zayıf kimliği olan nesneleri kilitlemeyin|  
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|SQL sorgularını güvenlik açıkları için gözden geçirin|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke dize bağımsız değişkenleri için hazırlama belirtin|  
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|Değer türleri üzerinde bildirimsel güvenliği gözden geçirin|  
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|İşaretçiler görünür olmamalıdır|  
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|Güvenli türler alanları açığa çıkarmamalıdır|  
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|Yöntem güvenliği türün bir üst kümesi olmalıdır|  
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|APTCA yöntemleri yalnızca APTCA yöntemlerini çağırmalıdır|  
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|APTCA türleri yalnızca APTCA taban türlerini genişletmelidir|  
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|Bağlantı talepleri olan yöntemleri dolaylı olarak açığa çıkarmayın|  
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|Geçersiz kılma bağlantı talepleri taban ile özdeş olmalıdır|  
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|Savunmasız sonunda yan tümcelerini dış sarmalayın|  
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|Tür bağlantı talepleri devralma taleplerini gerektirir|  
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|Güvenlik kritik türleri tür eşdeğerliğine katılamaz|  
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|Varsayılan oluşturucular en az taban tür varsayılan oluşturucular kadar kritik olmalıdır|  
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|Temsilciler tutarlı saydamlığı olan yöntemlere bağlanmalıdır|  
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır|  
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|Saydam yöntemler yalnızca doğrulanabilir IL içermelidir|  
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|Saydam yöntemler SuppressUnmanagedCodeSecurity özniteliğine sahip yöntemleri çağırmamalıdır|  
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|Saydam kod güvenlik kritik başvurmamalıdır|  
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|Saydam yöntemleri LinkDemands karşılamalıdır değil|  
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|Türler kendi taban türleri ve arabirimleri en az kadar kritik olmalıdır|  
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|Saydam yöntemler güvenlik kullanamazsınız onaylar|  
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|Saydam metotlar yerel kod içine çağırmamalıdır|  
|[CA2200](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|Yığın ayrıntılarını korumak için yeniden fırlatma|  
|[CA2202](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Nesneleri birden çok kez atmayın|  
|[CA2207](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Değer türü statik alanları satır içi başlatın|  
|[CA2212](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|Servis verilen bileşenleri WebMethod ile işaretlemeyin|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Atılabilen alanlar atılmalıdır|  
|[CA2214](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|Geçersiz kılınabilir yöntemleri oluşturucular içinde çağırmayın|  
|[CA2216](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|Atılabilir türler sonlandırıcıyı bildirmelidir|  
|[CA2220](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|Sonlandırıcılar taban Sonlandırıcıları çağırmalıdır|  
|[CA2229](../code-quality/ca2229-implement-serialization-constructors.md)|Serileştirme oluşturucularını uygulayın|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Eşittir işlecini ValueType.equals'ı geçersiz kılarak üzerinde|  
|[CA2232](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|İşareti Windows Forms giriş noktalarını STAThread ile işaretleyin|  
|[CA2235](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Tüm serileştirilebilir olmayan alanları işaretleyin|  
|[CA2236](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|ISerializable türler üzerinde taban sınıf yöntemlerini çağırın|  
|[CA2237](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|İşareti ISerializable türleri SerializableAttribute ile işaretleyin|  
|[CA2238](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Serileştirme yöntemlerini doğru uygulama|  
|[CA2240](../code-quality/ca2240-implement-iserializable-correctly.md)|ISerializable'ı doğru uygulayın|  
|[CA2241](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|Biçimlendirme yöntemlerine doğru bağımsız değişkenleri sağlayın|  
|[CA2242](../code-quality/ca2242-test-for-nan-correctly.md)|NaN için doğru sınayın|  
|[CA1008](../code-quality/ca1008-enums-should-have-zero-value.md)|Numaralandırmalar sıfır değerine sahip olmalıdır|  
|[CA1013](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)|Aşırı yükleme aşırı yükleme eşittir işlecini ekleme ve çıkarma|  
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|Harfleri yerelleştirilmiş parametreler olarak göndermeyin|  
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|Dizeleri büyük harfe normalleştirin|  
|[CA1806](../code-quality/ca1806-do-not-ignore-method-results.md)|Yöntem sonuçlarını yoksaymayın|  
|[CA1816](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|GC çağırın. IDisposable.Dispose doğru|  
|[CA1819](../code-quality/ca1819-properties-should-not-return-arrays.md)|Özellikler diziler döndürmemelidir|  
|[CA1820](../code-quality/ca1820-test-for-empty-strings-using-string-length.md)|Dize uzunluğunu kullanarak boş dizeler için sınayın|  
|[CA1903](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|Yalnızca hedeflenen çerçeveden API kullanın|  
|[CA2004](../code-quality/ca2004-remove-calls-to-gc-keepalive.md)|GC kaldırın. KeepAlive|  
|[CA2006](../code-quality/ca2006-use-safehandle-to-encapsulate-native-resources.md)|Yerel kaynakları kapsamak için SafeHandle kullanın|  
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|CLSCompliant olmayan özel durumları Genel işleyiciler içinde yakalayın|  
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|Salt okunur kesilebilir başvuru türleri bildirmeyin|  
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|Dizi alanları salt okunur değildir|  
|[CA2106 BİLDİRİMLERİN](../code-quality/ca2106-secure-asserts.md)|Bildirimlerin güvenliğini sağlayın|  
|[CA2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|GC çağırın. Yerel kaynaklar kullanırken KeepAlive|  
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|Özel arabirimleri karşılayan yöntemleri mühürleyin|  
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|Serileştirme oluşturucularının güvenliğini sağlayın|  
|[CA2121](../code-quality/ca2121-static-constructors-should-be-private.md)|Statik oluşturucular özel olmalıdır|  
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|Güvenlik kritik sabitleri saydam olmalıdır|  
|[CA2205](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Win32 API'sının yönetilen eşdeğerlerini kullanın|  
|[CA2215](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Atma yöntemleri taban sınıf atmayı çağırmalıdır|  
|[CA2221](../code-quality/ca2221-finalizers-should-be-protected.md)|Sonlandırıcılar korunmalıdır|  
|[CA2222](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Devralınan üye görünürlüğünü azaltmayın|  
|[CA2223](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|Üyeler dönüş türünden daha fazla tarafından farklı olmalıdır|  
|[CA2224](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Eşittir işlecini aşırı yüklemesi üzerinde geçersiz kılma değerine eşittir|  
|[CA2226](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|İşleçler simetrik aşırı yüklemelere sahip olmalıdır|  
|[CA2227](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Koleksiyon Özellikleri salt okunur olmalıdır|  
|[CA2239](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|İsteğe bağlı alanlar için seri halden çıkarma yöntemleri sağlar.|



