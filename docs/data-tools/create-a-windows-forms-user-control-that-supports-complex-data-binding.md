---
title: "Veri bağlama ile bir Windows Forms kullanıcı denetimi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding, user controls
- data binding, complex
- user controls [Visual Studio], complex data binding
ms.assetid: c8f29c2b-b49b-4618-88aa-33b6105880b5
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 8b23bfe7c30988a80904377e583a5a5f6d4cd2ff
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-windows-forms-user-control-that-supports-complex-data-binding"></a>Karmaşık veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma
Windows uygulamaları formlarda verileri görüntüleme, var olan denetimleri seçebilirsiniz **araç**, veya uygulamanızın standart denetimlerinde kullanılamıyor işlevsellik gerektiriyorsa özel denetimler yazabilirsiniz. Bu kılavuzda uygulayan bir denetimin nasıl oluşturulacağını gösterir <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>. Denetimleri uygulayan <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> içeren bir `DataSource` ve `DataMember` veriye bağlı özelliği. Bu tür denetimler benzer bir <xref:System.Windows.Forms.DataGridView> veya<xref:System.Windows.Forms.ListBox>  
  
 Denetim yazma hakkında daha fazla bilgi için bkz: [tasarım zamanında Windows Forms denetimleri geliştirme](/dotnet/framework/winforms/controls/developing-windows-forms-controls-at-design-time).  
  
 Veri bağlama senaryolarda kullanım için denetimleri yazarken aşağıdaki veri bağlama özniteliklerden birini yapması gerekir:  
  
|Veri bağlama öznitelik kullanımı|  
|-----------------------------------|  
|Uygulama <xref:System.ComponentModel.DefaultBindingPropertyAttribute> basit denetimlerinde gibi bir <xref:System.Windows.Forms.TextBox>, tek bir sütun (veya özelliği) veri görüntüleme. Daha fazla bilgi için bkz: [basit veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|  
|Uygulama <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.DataGridView>, veri listeleri (veya tablo) görüntüler. (Bu işlem bu izlenecek yol sayfasında açıklanan.)|  
|Uygulama <xref:System.ComponentModel.LookupBindingPropertiesAttribute> , denetimlerinde gibi bir <xref:System.Windows.Forms.ComboBox>, veri listeleri (veya tablo) görüntüleme ancak tek bir sütun veya özelliği sunmak de gerekir. Daha fazla bilgi için bkz: [arama veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).|  
  
 Bu kılavuz, bir tablodaki veri satırlarının görüntüleyen bir karmaşık denetim oluşturur. Bu örnekte `Customers` Northwind örnek veritabanı tablosundan. Karmaşık kullanıcı denetiminin Müşteriler tablosunda görüntüleneceği bir <xref:System.Windows.Forms.DataGridView> özel denetim içinde.  
  
 Bu gözden geçirme sırasında öğreneceksiniz nasıl yapılır:  
  
-   Yeni bir **Windows Forms uygulaması**.  
  
-   Yeni bir ekleme **kullanıcı denetimi** projenize.  
  
-   Görsel olarak kullanıcı denetimi tasarlayın.  
  
-   Uygulama `ComplexBindingProperty` özniteliği.  
  
-   İle bir veri kümesi oluşturma [veri kaynağı Yapılandırma Sihirbazı](../data-tools/media/data-source-configuration-wizard.png).  
  
-   Ayarlama **müşteriler** tablosundaki [veri kaynakları penceresi](add-new-data-sources.md) yeni karmaşık denetimi kullanmak için.  
  
-   Yeni Denetim ondan sürükleyerek ekleme **veri kaynakları penceresi** üzerine **Form1**.  
  
## <a name="prerequisites"></a>Önkoşullar  
Bu kılavuzda, SQL Server Express LocalDB ve Northwind örnek veritabanı kullanılır.  
  
1.  SQL Server Express LocalDB yoksa, araçtan yüklemek [SQL Server sürümleri indirme sayfasına](https://www.microsoft.com/en-us/server-cloud/Products/sql-server-editions/sql-server-express.aspx), aracılığıyla veya **Visual Studio yükleyicisi**. Visual Studio Yükleyicisi'nde, SQL Server Express LocalDB parçası olarak yüklenebilir **veri depolama ve işleme** iş yükü veya tek bir bileşen olarak.  
  
2.  Northwind örnek veritabanı, şu adımları izleyerek yükleyin:  

    1. Visual Studio'da açın **SQL Server Nesne Gezgini** penceresi. (SQL Server Nesne Gezgini parçası olarak yüklü **veri depolama ve işleme** Visual Studio yükleyicisi iş yükündeki.) Genişletme **SQL Server** düğümü. Yerel veritabanı örneğinde sağ tıklatıp **yeni sorgu...** .  

       Sorgu Düzenleyicisi penceresini açar.  

    2. Kopya [Northwind Transact-SQL betiği](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) panonuza. Bu T-SQL betiği sıfırdan Northwind veritabanı oluşturur ve veri ile doldurur.  

    3. T-SQL betiği sorgu düzenleyicisine yapıştırın ve ardından **yürütme** düğmesi.  

       Kısa bir süre sonra sorgu yürütme tamamlandıktan ve Northwind veritabanı oluşturulur.  
  
## <a name="create-a-windows-forms-application"></a>Bir Windows Forms uygulaması oluşturma  
 İlk adım oluşturmaktır bir **Windows Forms uygulaması**.  
  
#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **ComplexControlWalkthrough**ve ardından **Tamam**. 
  
     **ComplexControlWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  
  
## <a name="add-a-user-control-to-the-project"></a>Projeye bir kullanıcı denetimi Ekle  
 Bu kılavuzda karmaşık veri bağlanabilir denetimden oluşturduğundan bir **kullanıcı denetimi**, eklemelisiniz bir **kullanıcı denetimi** proje öğesi.  
  
#### <a name="to-add-a-user-control-to-the-project"></a>Bir kullanıcı denetimi projeye eklemek için  
  
1.  Gelen **proje** menüsünde seçin **kullanıcı denetimi Ekle**.  
  
2.  Tür **ComplexDataGridView** içinde **adı** alan ve ardından **Ekle**.  
  
     **ComplexDataGridView** denetim eklenen **Çözüm Gezgini**ve Tasarımcısı'nda açılır.  
  
## <a name="design-the-complexdatagridview-control"></a>Tasarım ComplexDataGridView denetimi  
 Bu adım ekler bir <xref:System.Windows.Forms.DataGridView> kullanıcı denetimi için.  
  
#### <a name="to-design-the-complexdatagridview-control"></a>Tasarım ComplexDataGridView denetimi  
  
-   Sürükleme bir <xref:System.Windows.Forms.DataGridView> gelen **araç** kullanıcı denetiminin tasarım yüzeyine.  
  
## <a name="add-the-required-data-binding-attribute"></a>Gerekli veri bağlama öznitelik Ekle  
 Karmaşık, destek veri bağlama denetimleri için uygulayabileceğiniz <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>.  
  
#### <a name="to-implement-the-complexbindingproperties-attribute"></a>ComplexBindingProperties özniteliği uygulamak için  
  
1.  Anahtar **ComplexDataGridView** denetim kodu görüntülemek için. (Üzerinde **Görünüm** menüsünde, select **kod**.)  
  
2.  Kodla `ComplexDataGridView` aşağıdaki:  
  
     [!code-csharp[VbRaddataDisplaying#4](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#4](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.vb)]  
  
3.  Gelen **yapı** menüsünde seçin **yapı çözümü**.  
  
## <a name="creating-a-data-source-from-your-database"></a>Veritabanından veri kaynağı oluşturma  
Bu adımı kullanan **veri kaynağı yapılandırması** bir veri kaynağı oluşturmak için Sihirbazı'nı temel alarak `Customers` Northwind örnek veritabanı tablosunda.  
  
#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için  
  
1.  Üzerinde **veri** menüsünde tıklatın **veri kaynaklarını Göster**.  
  
2.  İçinde **veri kaynakları** penceresinde, seçin **yeni veri kaynağı Ekle** başlatmak için **veri kaynağı yapılandırması** Sihirbazı.  
  
3.  Seçin **veritabanı** üzerinde **bir veri kaynağı türü seç** sayfasında ve ardından **sonraki**.  
  
4.  Üzerinde **veri bağlantınızı seçin** sayfasında aşağıdakilerden birini yapın:  
  
    -   Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.  
  
    -   Seçin **yeni bağlantı** başlatmak için **Ekle/Değiştir bağlantı** iletişim kutusu.  
  
5.  Veritabanınız bir parola gerektiriyorsa, hassas bilgileri Ekle ve ardından seçeneğini **sonraki**.  
  
6.  Üzerinde **bağlantı dizesi için uygulama yapılandırma dosyasını kaydetmek** sayfasında, **sonraki**.  
  
7.  Üzerinde **veritabanı nesnelerini seçin** sayfasında **tabloları** düğümü.  
  
8.  Seçin `Customers` tablo ve ardından **son**.  
  
     **NorthwindDataSet** projenize, eklenen ve `Customers` tablo görünür **veri kaynakları** penceresi.  
  
## <a name="set-the-customers-table-to-use-the-complexdatagridview-control"></a>Müşteriler tablosu ComplexDataGridView denetimi kullanmak için ayarlama  
 İçinde **veri kaynakları** penceresinde formunuza öğeleri sürükleme önce oluşturulacak denetim ayarlayabilirsiniz.  
  
#### <a name="to-set-the-customers-table-to-bind-to-the-complexdatagridview-control"></a>ComplexDataGridView denetimi bağlamak için Müşteriler tablosu ayarlamak için  
  
1.  Açık **Form1** Tasarımcısı'nda.  
  
2.  Genişletme **müşteriler** düğümünde **veri kaynakları** penceresi.  
  
3.  Aşağı açılan oku tıklatın **müşteriler** düğümü seçin **Özelleştir**.  
  
4.  Seçin **ComplexDataGridView** listesinden **ilişkili denetimleri** içinde **veri UI özelleştirme seçenekleri** iletişim kutusu.  
  
5.  Aşağı açılan oku tıklatın `Customers` tablo ve seçin **ComplexDataGridView** denetim listesinde.  
  
## <a name="add-controls-to-the-form"></a>Forma denetimler ekleme  
 Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** formunuza penceresi.  
  
#### <a name="to-create-data-bound-controls-on-the-form"></a>Form üzerinde veri bağlama denetimleri oluşturmak için  
  
-   Ana sürükleyin **müşteriler** düğümden **veri kaynakları** forma penceresi. Doğrulayın **ComplexDataGridView** denetimi tablonun verileri görüntülemek için kullanılır.  
  
## <a name="running-the-application"></a>Uygulamayı çalıştırma  
  
#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için  
  
-   Uygulamayı çalıştırmak için F5 tuşuna basın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Uygulama gereksinimlerinize bağlı olarak, veri bağlamayı destekleyen bir denetim oluşturma sonra gerçekleştirmek istediğinizi düşünelim birkaç adım vardır. Bazı tipik sonraki adımlar şunlardır:  
  
-   Diğer uygulamalarda yeniden kullanabileceğiniz şekilde bir Denetim Kitaplığı'nda özel denetimler yerleştirme.  
  
-   Arama senaryoları desteklemek denetimler oluşturma. Daha fazla bilgi için bkz: [arama veri bağlamayı destekleyen bir Windows Forms kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)   
 [Windows Forms denetimleri](/dotnet/framework/winforms/controls/index)