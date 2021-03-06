---
title: İş Akışı Tasarımcısı - Send etkinlik Tasarımcısı
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.Send.UI
ms.assetid: b514f2e4-767c-4b94-ac61-dd3a54d4b96d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7cbbcc01001d663e927431b99915bf69d9a223ce
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49836430"
---
# <a name="send-activity-designer"></a>Send Etkinlik Tasarımcısı

**Gönder** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.ServiceModel.Activities.Send> etkinlik.

## <a name="the-send-activity"></a>Gönder etkinliği

 A <xref:System.ServiceModel.Activities.Send> etkinliği, bir hizmete ileti göndermek için kullanılır. A <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik bağlanabilir bir <xref:System.ServiceModel.Activities.Send> istek/yanıt ileti değişim deseni istemcide bir parçası olarak bir ileti aldığı etkinlik.

### <a name="using-the-send-activity-designer"></a>Send etkinlik Tasarımcısı kullanma

Erişim **Gönder** etkinlik Tasarımcısı'nda **Mesajlaşma** kategorisi **araç kutusu**. **Gönder** etkinlik Tasarımcısı, gelen sürüklenebilir **araç kutusu** ve etkinlikleri genellikle yerleştirilen her yerde iş akışı Tasarımcısı yüzeyine açın. Bu, oluşturur bir <xref:System.ServiceModel.Activities.Send> etkinliği ile bir varsayılan <xref:System.Activities.Activity.DisplayName%2A> , gönderme. <xref:System.Activities.Activity.DisplayName%2A> Üst bilgisinde düzenlenebilir **Gönder** etkinlik Tasarımcısı veya **DisplayName** özellik kılavuzunda kutusu.

Oluşturmak için bir <xref:System.ServiceModel.Activities.ReceiveReply> etkinlik ve seçili bağlama <xref:System.ServiceModel.Activities.Send> etkinlik, sağ **göndermek** etkinlik Tasarımcısı tıklayın **ReceiveReply oluşturma** bağlam menüsü öğesini ve **ReceiveReplyForSend** Tasarımcısı aşağıda görünür **Gönder** Tasarımcısı. <xref:System.ServiceModel.Activities.ReceiveReply> Etkinlik dışı bir etkinlik, bir istek/yanıt ileti değişim deseni istemcide bir parçası olarak bir ileti alır. İle yapılandırılabilir **ReceiveReplyForSend** Tasarımcısı.

Alternatif olarak, **SendAndReceiveReply** şablonu Tasarımcısı'nda **Mesajlaşma** kategorisi **araç kutusu** önceden yapılandırılmış çiftioluşturmakiçinkullanılan<xref:System.ServiceModel.Activities.Send>ve <xref:System.ServiceModel.Activities.ReceiveReply> etkinlikler. Kullanımıyla ilgili daha fazla bilgi için **SendAndReceiveReply** ve **ReceiveReplyForSend** şablonları, [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) konu.

### <a name="the-send-activity-properties"></a>Send etkinlik özellikleri

Aşağıdaki tabloda <xref:System.ServiceModel.Activities.Send> özellikleri Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, Özellikler kılavuzu veya iş akışı Tasarımcısı yüzeyine düzenlenebilir.


| Özellik adı | Gerekli | Kullanım |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | Kolay adı <xref:System.ServiceModel.Activities.Send> etkinlik. Gönderme varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> kati şekilde gerekli değil kullanmak için en iyi bir uygulamadır. |
| <xref:System.ServiceModel.Activities.Send.OperationName%2A> | Doğru | Hizmet işlemi adını adlı bu <xref:System.ServiceModel.Activities.Send> etkinlik. Bu özellik için varsayılan değer oluşturmak için kullanılan **eylem** özelliği varsa **eylem** özelliği açıkça ayarlanmadı. |
| <xref:System.ServiceModel.Activities.Send.ServiceContractName%2A> | Doğru | Çağrılacak hizmet uygulayan hizmet sözleşmesi adı. |
| <xref:System.ServiceModel.Activities.Send.Content%2A> | False | İleti veya parametre içeriği almak için belirtir. Ya da olabilir bir <xref:System.ServiceModel.Activities.ReceiveMessageContent> etkinlik veya <xref:System.ServiceModel.Activities.ReceiveParametersContent> etkinlik. Bu özelliğin yanındaki üç nokta düğmesini seçerek Düzenle **içerik** özellik kılavuzu veya tıklayarak alanındaki **tanımlayın...**  yanında düğmesini **içerik** üzerinde etiket **alma** etkinlik Tasarımcı yüzeyine bırakın. Her ikisini de görüntüle **içerik tanımı** iletişim. Bu kutuyu kullanma hakkında daha fazla bilgi için bkz. [içerik tanımı iletişim kutusunun](../workflow-designer/content-definition-dialog-box.md) konu. |
| <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> | False | Belirtir <xref:System.ServiceModel.Activities.CorrelationHandle> uygun iş akışı örneği için ileti yönlendirmek için kullanılır.<br /><br /> Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Send.CorrelatesWith%2A> özelliği açmak için özellikler kılavuzundaki **ifade Düzenleyicisi** iletişim kutusu. Bu iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz. [nasıl yapılır: ifade düzenleyicisini kullanma](../workflow-designer/how-to-use-the-expression-editor.md) konu. |
| <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> | False | Koleksiyonunu belirtir <xref:System.ServiceModel.Activities.CorrelationInitializer> birden çok başlatmak nesneleri <xref:System.ServiceModel.Activities.CorrelationHandle> bu yapılandırma nesneleri <xref:System.ServiceModel.Activities.Send> etkinlik iş akışı içinde. Yanındaki üç nokta düğmesini tıklayın <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> özelliği açmak için özellikler kılavuzundaki **bağıntı başlatıcılar Ekle** iletişim kutusu. Bu kutuyu kullanma hakkında daha fazla bilgi için bkz. [Correlationınitializer iletişim kutusunu](../workflow-designer/add-correlationinitializers-dialog-box.md) konu. |
| <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> | False | Bir koleksiyon hizmet işlemi için bilinen türleri bu tarafından çağrılacak <xref:System.ServiceModel.Activities.Send> etkinlik. Bu özellik ile birlikte kullanılması gereken <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> özelliğini <xref:System.Runtime.Serialization.DataContractSerializer>. Varsa göz ardı edilir <xref:System.Xml.Serialization.XmlSerializer> kullanılır.<br /><br /> Yanında bulunan üç nokta düğmesini seçin **KnownTypes** özellik kılavuzunda görüntülenecek alan **Editor Typu Kolekce** ilgili türleri ile ekleyebileceğiniz iletişim.<br /><br /> Yanında bulunan üç nokta düğmesini seçin **KnownTypes** özellik kılavuzunda görüntülenecek alan **Editor Typu Kolekce** ilgili türleri ile ekleyebileceğiniz iletişim kutusu. Bu kutuyu kullanma hakkında daha fazla bilgi için bkz. [türü koleksiyon Düzenleyicisi iletişim kutusu](../workflow-designer/type-collection-editor-dialog-box.md) konu. |
| <xref:System.ServiceModel.Activities.Send.ProtectionLevel%2A> | Doğru | Belirtir <xref:System.Net.Security.ProtectionLevel> ileti.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> yalnızca kimlik doğrulamasını anlamına gelir.<br />2. <xref:System.Net.Security.ProtectionLevel> oturum iletilen veri bütünlüğünü sağlamaya yardımcı olmak için veri anlamına gelir.<br />3. <xref:System.Net.Security.ProtectionLevel> anlamına gelir, şifreleme ve veri gizliliği ve aktarılan veri bütünlüğünü sağlamaya yardımcı olmak için oturum açın. |
| <xref:System.ServiceModel.Activities.Send.SerializerOption%2A> | Doğru | Çağrılacak hizmet işlemi için kullanılacak serileştirici <xref:System.ServiceModel.Activities.Send> etkinlik. Varsayılan değer <xref:System.Runtime.Serialization.DataContractSerializer>, serileştirir ve bir örneği bir XML akışı veya belge kullanarak sağlanan veri anlaşması türü seri durumdan çıkarır. |
| <xref:System.ServiceModel.Activities.Send.Action%2A> | False | İletinin eylem üstbilgisini belirtir. Değeri açıkça ayarlanmazsa, varsayılan: https://tempuri.org/{service sözleşme ad alanı} / {hizmet sözleşmesi adı} / {işlem adı}. Belirtilen varsa bir <xref:System.ServiceModel.Activities.Send> etkinliği <xref:System.ServiceModel.Activities.Receive> iletiyi alır etkinliği iletisinin doğru bir şekilde teslim edilmesi aynı değere sahip olmalıdır. |
| <xref:System.ServiceModel.Activities.Send.TokenImpersonationLevel%2A> | | <xref:System.Security.Principal.TokenImpersonationLevel> İleti alıcısı için izin verilir. Bu, bir sunucu işlemi adına bir istemci işlemi görev yapabilir derece yöneten kimliğe bürünme güvenlik düzeyleri tanımlar.<xref:System.Security.Principal.TokenImpersonationLevel> Kimliğe bürünme düzeyi atanmadı gösterir. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemci kimlik bilgilerini alamaz ve istemci bürünülemedi gösterir. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi güvenlik tanımlayıcıları ve ayrıcalıkları gibi istemci hakkındaki bilgileri elde edebilirsiniz, ancak istemci bürünülemedi gösterir. Örneğin, tablolar ve görünümler dışarı veritabanı ürünleri kendi nesneleri dışarı aktarın ve sunucular için kullanışlıdır. Alınan istemci güvenlik bilgileri kullanarak, sunucu erişimi doğrulaması istemcinin güvenlik bağlamını kullanarak diğer hizmetleri kullanmaya olmadan kararlar verebilirsiniz. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemci güvenlik bağlamı, yerel sistemde bürünebileceğini gösterir. Sunucu, uzak sistemlere istemci kimliğine bürünme olamaz. <xref:System.Security.Principal.TokenImpersonationLevel> Sunucu işlemi istemci güvenlik bağlamı uzak sistemler bürünebileceğini gösterir. |
| <xref:System.ServiceModel.Activities.Send.Endpoint%2A> | | <xref:System.ServiceModel.Endpoint> , <xref:System.ServiceModel.Activities.Send> Etkinlik iletiyi gönderir. Bu özellik ayarlanırsa <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> özelliği ayarlanmalıdır **null**. |
| <xref:System.ServiceModel.Activities.Send.EndpointAddress%2A> | | <xref:System.ServiceModel.EndpointAddress> İletinin gönderildiği için. |
| <xref:System.ServiceModel.Activities.Send.EndpointConfigurationName%2A> | | Uç nokta Yapılandırması adı. Bu özellik, bir uç nokta yapılandırma dosyasında yapılandırırken ayarlanır. Bu özellik verilen adı olarak ayarlanmalıdır  **\<uç noktası >** yapılandırma dosyanızdaki öğesi. Bu özellik ayarlanırsa <xref:System.ServiceModel.Activities.Send.Endpoint%2A> özelliği ayarlanmalıdır **null**. |

## <a name="see-also"></a>Ayrıca bkz.

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)