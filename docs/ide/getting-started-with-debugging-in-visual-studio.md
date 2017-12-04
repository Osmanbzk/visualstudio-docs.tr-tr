---
title: "Visual Studio'da hata ayıklamaya başlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3a14d28-d811-4ff3-bd09-21dce14025ca
caps.latest.revision: "5"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 82bce617eec0f5038499a2eed370efa33d817e20
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-with-debugging-in-visual-studio"></a>Visual Studio'da hata ayıklamaya başlama
Visual Studio Proje derleme ve hata ayıklama araçları güçlü tümleşik kümesi sağlar. Bu konuda, kullanıcı Arabirimi özelliklerini hata ayıklama en temel kümesi'ni kullanmaya başlamak öğrenin.  

 Not: Bu sayfasının en altında daha gelişmiş özellikleri ve platform veya özelliklerle ilgili konulara bağlantılar aynıdır.  

## <a name="my-code-doesnt-work-help-me-visual-studio"></a>Kodumu işe yaramaz. Bana, Visual Studio Yardım!  
 Out Düzenleyicisi dahil edilir böylece ve bazı kodlar oluşturduysanız. Şimdi, bu kod hata ayıklamayı başlatmak istiyor. Visual Studio'da çoğu IDE gibi ile hata ayıklama için iki aşama vardır: yakalamak ve proje ve derleyici hataları; çözümlemek için kod oluşturma Bu kodu yakalamak ve çalışma zamanı ve dinamik hatalarını gidermek için ortamında ve çalıştırma.  

### <a name="configuring-a-build"></a>Bir yapı yapılandırma  
 Yapı yapılandırması iki temel tür vardır: **hata ayıklama** ve **sürüm**. İlk yapılandırmayı daha zengin etkileşimli çalışma zamanı hata ayıklama için bir deneyim sağlar, ancak hiçbir zaman sevk gereken daha yavaş ve daha büyük bir yürütülebilir üretir. İkinci sevk etmek uygun olan bir daha hızlı ve daha iyileştirilmiş yürütülebilir dosyası oluşturur (en az derleyici perspektifinden).  

 Varsayılan derleme yapılandırma **hata ayıklama**.  

 ![Visual Studio hata ayıklama Oluştur düğmesini](../ide/media/vs_ide_gs_debug_build_type1.PNG "Vs_ide_gs_debug_build_type1")  

 Gibi belirli yapı platform, hedeflenecek belirtebilirsiniz **x86** (32-bit Intel CPU) **x64** (64-bit Intel CPU) ve **ARM** (ARM CPU'lar, yalnızca belirli uygulama için desteklenir türleri için). Varsayılan değer **x86** yönetilen ve yerel projeleri için. Değiştirmek için derleme platform açılan tıklayın ve farklı bir platform seçin veya **Configuration Manager...**  

 ![Visual Studio yapılandırma dosyası Yöneticisi penceresi](../ide/media/vs_ide_gs_debug_build_cf_mgr.PNG "Vs_ide_gs_debug_build_cf_mgr")  

 Hedeflenen yapı yapılandırmayla belirtebilirsiniz **Configuration Manager**. Başlatın, tıklatın **yapılandırma** veya **CPU** açılan listesinde seçip **yeni...**  yeni derleme veya platform oluşturmak için.  

 ![Visual Studio Configuration Manager penceresi](../ide/media/vs_ide_gs_debug_build_cf_mgr_2.PNG "Vs_ide_gs_debug_build_cf_mgr_2")  

 Çıkış başlangıç yalnızca kullanırsınız **hata ayıklama** ve **x86** yapı yapılandırması ve platformu, sırasıyla. Kodlama ve hata ayıklama bittiğinde, yapılandırmaya değiştirme **sürüm** ve belirli bir platformun hedefleyebilirsiniz. (Sağlanan Visual Studio'nun daha eski sürümleri bir **AnyCPU** .Net kod projeleri için varsayılan platform.)  

 Not: projenizi yapılandırdığınızda, yapılandırma ve platform değerler Ayrıca hangi proje dizin yolu yürütülebilir depolamak için oluşturduğunuz belirlemek için kullanılır. Genel olarak,  **\<yolu Proje >\\< proje-adı >\\< yapılandırma\>\\< platform\>**. Örneğin, bir proje `Debug` ve bir platforma `x86` altında bulunan `Projects\MyProjectNameHere\MyProjectNameHere\bin\Debug\x86`. Bu, kendi Araçlar ya da bu yerleşik yürütülebilir dosyaları yönetmek komut dosyaları varsa yararlı olabilir.  

### <a name="building-your-code"></a>Kod oluşturma  
 Yapınızın ile yapılandırılmış gerçekte projenizi derleme için zaman yapılır. F7, ancak basmak için bunu yapmanın en kolay yolu da yapı seçerek başlatabilirsiniz **Yapı Çözümü Derle ->** ana menüden.  

 ![Visual Studio Proje menüsü Seçimi Yapı](../ide/media/vs_ide_gs_debug_build_menu_item.png "Vs_ide_gs_debug_build_menu_item")  

 Yapı işleminde gözleyebilirsiniz **çıkış** Visual Studio kullanıcı arabirimini ekranın alt kısmındaki durum penceresi. Hataları, uyarıları ve yapı işlemleri burada görüntülenir. Hataları (veya yapılandırılmış bir düzeyin üzerinde bir uyarı varsa) varsa, derleme başarısız olur. Hataları ve Uyarıları nerede oluştuğunu satıra gitme tıklatabilirsiniz. Projenizi yeniden oluşturun ya da tuşlarına basarak **F7** yeniden (yalnızca hatalar dosyalarıyla yeniden derleyin için) veya **Ctrl + Alt + F7** (için temiz ve eksiksiz rebuild).  

 Düzenleyici aşağıda Sonuçları penceresinde sekmeli windows iki yapı vardır: **çıkış** (hata iletileri de dahil olmak üzere) çıkış; ham derleyici içeren pencere ve **hata listesi** penceresinde hangi tüm hataların ve uyarıların sıralanabilir ve filtrelenebilir listesini sağlar.  

 Başarılı olduğunda, bu şekilde sonuçları görürsünüz **çıkış** penceresi.  

 ![Visual Studio başarılı yapı çıktısını](../ide/media/vs_ide_gs_debug_success_build.PNG "vs_ide_gs_debug_success_build")  

### <a name="reviewing-the-error-list"></a>Hata listesi gözden geçirme  
 Daha önce ve başarılı bir şekilde derledik kod değişiklik yapmış olduğunuz sürece, muhtemelen bir hata vardır. Kodlama için yeniyseniz, bunları çok sayıda'de vardır. Hataları bazen belirgin gibi basit sözdizimi hatası veya hatalı değişken adı ve bazı durumlarda, size yol göstermesi için yalnızca bir şifreli koduyla anlamak zordur. Sorunları temizleyici görünümü için derleme alt kısmına gidin **çıkış** penceresi ve tıklatın **hata listesi** sekmesi. Bu hataları ve Uyarıları projeniz için daha düzenli bir görünümünü sürer ve bazı ek seçenekler de sunar.  

 ![Visual Studio çıkış ve hata listesi](../ide/media/vs_ide_gs_debug_bad_build_error_list.PNG "Vs_ide_gs_debug_bad_build_error_list")  

 Tıklatın hata satırında **hata listesi** penceresini açın ve hata oluşuyor satır atlanır. (Veya satır numaralarını tıklayarak açmak **hızlı başlatma** "numaraları içine satır" yazın ve Enter tuşuna basarak sağ üst, çubuğunda. Bu almak için en hızlı yoludur **seçenekleri** Burada, açmanız satır numaralarını penceresi girişi. Kullanmayı öğrenin **hızlı başlatma** çubuğunu ve kendiniz çok UI tıklama kaydedin!)  

 ![Satır numaraları ile Visual Studio düzenleyicisinde](../ide/media/vs_ide_gs_debug_line_numbers.png "Vs_ide_gs_debug_line_numbers")  

 ![Visual Studio satır numaraları seçeneği](../ide/media/vs_ide_gs_debug_options_line_numbers.png "Vs_ide_gs_debug_options_line_numbers")  

 Hatanın oluştuğu satır numarası hızla atlamak için CTRL + G kullanın.  

 Hata bir kırmızı "dalgalı çizgi" alt çizgi tarafından tanımlanır. Daha fazla ayrıntı için üzerine gelin. Düzeltme yapın ve düzeltmeler ile yeni bir hata neden olabilir ancak bu, kaybolur. (Bu bir "gerileme" olarak adlandırılır.)  

 ![Visual Studio hata vurgulu](../ide/media/vs_ide_gs_debug_error_hover1.png "Vs_ide_gs_debug_error_hover1")  

 Hata listesi yol ve kodunuzdaki tüm hataları çözün.  

 ![Visual Studio hata ayıklama hataları penceresi](../ide/media/vs_ide_gs_debug_error_list.PNG "Vs_ide_gs_debug_error_list")  

### <a name="reviewing-errors-in-detail"></a>Ayrıntılı hataları gözden geçirme  
 Birçok hata hiçbir derleyici şartlarında oldukları gibi tümcecik oluşturulmuş sizin için anlamlı olabilir. Bu durumda, ek bilgilere ihtiyacınız olacaktır. Gelen **hata listesi** penceresi, hata (veya uyarı) ile ilgili giriş satırına sağ tıklayıp seçerek hakkında daha fazla bilgi için otomatik bir Bing arama yapabilir **hata yardımını göster** gelen bağlam menüsü.  

 ![Visual Studio hata listesi Bing arama](../ide/media/vs_ide_gs_debug_error_list_error_help.png "Vs_ide_gs_debug_error_list_error_help")  

 Bu sekme Visual Studio içinde barındıran bir Bing sonuçlarını hata kodu ve metin arama başlatır. Internet üzerindeki birçok farklı kaynaktan sonuçlar olur ve tüm yararlı olabilir.  

 Alternatif olarak, köprülü hata kodu değeri tıklatabilirsiniz **kod** sütunu **hata listesi**. Bu yalnızca hata kodu için Bing arama başlatır.  

### <a name="performing-static-code-analysis"></a>Statik kod çözümlemesi gerçekleştirme  
 "Statik kod analizi", "kodumu çalışma zamanı hataları neden olabilecek yaygın sorunlar veya kod yönetimi sorunları için otomatik olarak denetle" etkisine süslü bir yoludur. Yapı önleme belirgin hataları temizledikten sonra onu çalıştıran biri alýþkanlýk almak ve bunu üretebilir uyarıları gidermek için biraz zaman alabilir. Kendiniz bazı zorlukların yol aşağı Kaydet yanı birkaç kod stili teknikleri öğrenin.  

 Alt + F11 tuşlarına basarak (veya seçin **Çözümle -> Çalıştır Kod Analizi çözüm üzerinde** üstteki menüden) statik kod analizi başlatmak için. Çok fazla kod varsa, bu biraz zaman alabilir.  

 ![Visual Studio Kod Analizi menü öğesi](../ide/media/vs_ide_gs_debug_run_code_analysis.png "Vs_ide_gs_debug_run_code_analysis")  

 Tüm yeni veya güncelleştirilmiş uyarılar görünür **hata listesi** IDE ekranın alt kısmındaki sekme. Bunları atlamak için Uyarılar'ı tıklatın.  

 ![Visual Studio hata listesi uyarılarla](../ide/media/vs_ide_gs_debug_code_analysis_warning_error_list.PNG "vs_ide_gs_debug_code_analysis_warning_error_list")  

 Uyarılar yerine kırmızı bir açık sarı yeşil dalgalı ile tanımlanır. Daha fazla ayrıntı için üzerlerine getirin ve bunları düzeltmeleri veya yeniden düzenleme seçenekleri yardımcı olmak için bir bağlam menüsü almak için sağ tıklayın.  

 ![Visual Studio kod çözümleme uyarısı vurgulu](../ide/media/vs_ide_gs_debug_code_analysis_warning_hover.png "vs_ide_gs_debug_code_analysis_warning_hover")  

### <a name="using-light-bulbs-to-fix-or-refactor-code"></a>Ampuller düzeltmek veya kodu yeniden kullanma  
 Ampuller sağlayan Visual Studio için yeni bir özellik olan kodu satır içi yeniden düzenleyin. Sık kullanılan uyarılar düzeltmek için kolay bir yol oldukları hızlı ve etkili şekilde. Bunlara erişmek için bir uyarı dalgalı sağ tıklayın (veya Ctrl +'tuşuna basın. Dalgalı bekleyerek), çalışırken ve ardından **hızlı Eylemler**.  

 ![Visual Studio ampul hızlı seçenekleri](../ide/media/vs_ide_gs_debug_light_bulb1.png "Vs_ide_gs_debug_light_bulb1")  

 Olası düzeltmeler veya bu kod satırına uygulayabilirsiniz refactors listesini görürsünüz.  

 ![Visual Studio ampul Önizleme](../ide/media/vs_ide_gs_debug_light_bulb_preview_changes.PNG "Vs_ide_gs_debug_light_bulb_preview_changes")  

 Ampuller, düzenleme, düzeltmek veya kodunuzu iyileştirmek için bir fırsat kodu çözümleyiciler belirlemek her yerde kullanılabilir. Herhangi bir kod satırında, bağlam menüsünü açmak için sağ tıklayıp **hızlı seçenekleri** (ya da verimlilik tercih ederseniz, tekrar, Ctrl + tuşlarına basın.). Yeniden düzenleme veya geliştirme seçenekleri kullanılabilir alanı varsa, bunlar görüntülenir; Aksi takdirde, ileti `No quick options available here` IDE sol alt köşesinde çerçeve içinde görüntülenir.  

 ![Visual Studio ampul 'seçeneği' metin](../ide/media/vs_ide_gs_debug_light_bulb_no_options.PNG "Vs_ide_gs_debug_light_bulb_no_options")  

 Deneyim, ok tuşları ve Ctrl + hızlı bir şekilde kullanabilirsiniz. Hızlı fırsatları yeniden düzenleme seçeneği işaretleyin ve kodunuzu temizlemek amacıyla!  

 Ampuller hakkında daha fazla bilgi için okuma [ampullerle hızlı eylemler gerçekleştirme](../ide/perform-quick-actions-with-light-bulbs.md).  

### <a name="debugging-your-running-code"></a>Çalışan kodda hata ayıklama  
 Başarıyla kodunuzu yerleşik artık ve biraz temizleme gerçekleştirilen göre çalıştırın F5 tuşuna basarak veya seçerek **hata ayıklama -> hata ayıklamayı Başlat**. Ayrıntılı kendi davranış gözlenir şekilde bu bir hata ayıklama ortamında uygulamanızı başlatacak. Visual Studio IDE değişiklikleri uygulamanızı çalışırken: **çıkış** penceresi (varsayılan yapılandırmasında penceresi), iki yenilerini almıştır **otomobiller/Yereller/modülleri/izleme** sekmeli pencere ve  **Çağrı yığını/kesme noktaları/özel durum ayarları/çıkış** sekmeli penceresi. Bu windows inceleyebilir ve çalışırken, uygulamanızın değişkenleri, iş parçacıkları, çağrı yığınları ve çeşitli diğer davranışlarını değerlendirmek olanak tanıyan birden fazla sekme sahip.  

 ![Visual Studio otomobiller ve çağrı yığınını Windows](../ide/media/vs_ide_gs_debug_autos_and_call_stack.PNG "Vs_ide_gs_debug_autos_and_call_stack")  

 Uygulamanız ile çeşitli eylemler deneyin ve değişiklikleri gözlemleyin. Ctrl + Alt + Break tuşlarına basarak uygulamayı bir şey anormal görünüyorsa, duraklatmak (veya tıklayın **duraklatma** düğmesi).  

 ![Visual Studio bölün tüm düğmesi](../ide/media/vs_ide_gs_debug_break_all_button.png "vs_ide_gs_debug_break_all_button")  

 Uygulama çalıştırmaya devam etmek için F5 tuşuna basın (veya **devam** düğmesi).  

 ![Visual Studio hata ayıklama devam düğmesine](../ide/media/vs_ide_gs_debug_continue_button.png "Vs_ide_gs_debug_continue_button")  

 Shift + F5'e basarak veya tıklatarak uygulamanızı durdurabilirsiniz **durdurmak** düğmesi. Veya, yalnızca uygulamanın ana penceresinde (veya komut satırı iletişim) kapatabilirsiniz.  

 Kodunuzu mükemmel çalıştırdıysanız ve tam olarak beklenen, Tebrikler! Derleme yapılandırmasını değiştirme **sürüm** ve dağıtım için yeniden! (Uzmanları için bit birim testi sonunda, ancak atlamak istediğiniz.) Ancak, askıda, veya kilitlendi veya bazı garip sonuçları vermiş, bu sorunların kaynağı bulmak ve hataları düzeltmek gerekir.  

### <a name="setting-simple-breakpoints"></a>Basit kesme noktalarını ayarlama  
 Kesme noktaları güvenilir hata ayıklama en temel ve temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız veya kod dalı çalıştırmak destekleyip desteklemediğini belirtir. Ayarlama ve kesme noktaları kaldırma sonrasında bir projeyi yeniden gerekmez.  

 Gerçekleşirse veya kod satırı seçin ve F9 tuşuna sonu istediğiniz kadar boşlukta satırının tıklatarak bir kesme noktası ayarlayın. Kodunuzu çalıştırdığınızda, bu kod satırı yönergelerini yürütülmeden önce durdurur.  

 ![Visual Studio kesme noktası](../ide/media/vs_ide_gs_debug_breakpoint1.png "Vs_ide_gs_debug_breakpoint1")  

 Kod böldüğünde işaretli kod satırı ile henüz yürüttü değil. Bu noktada, kesme noktası tarafından işaretlenen kod satırı ile ilgili yönergeleri yürütmek ve değiştirilmiş değerleri incelemek isteyebilirsiniz. Bu, "içine kod atlama" adı verilir. İşaretli kodu yöntem çağrısı ise, içine F11 tuşlarına basarak geçebilirsiniz. Aynı zamanda "üzerinden kod satırı F10 tuşlarına basarak geçebilirsiniz". Atlama kodu hakkında daha fazla ayrıntı için okuma [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md).  

 Kesme noktaları için yaygın kullanımları şunlardır:  

1.  Kilitlenme veya askı kaynağı daraltmak için bunları boyunca ve hataya neden olduğunu düşündüğünüz yöntem çağrısı kodunu çözmek dağılım. Kod üzerinden adım olarak, kaldırmak ve soruna neden olan kod satırı ile bulana kadar yakın kesme noktaları birlikte sıfırlayın.  

2.  Yeni kod aldığımızda ve beklendiği şekilde davrandığından emin olmak için kod aracılığıyla adım başında bir kesme noktası ayarlayın.  

3.  Karmaşık bir davranış uyguladıysanız, program böldüğünde değişkenleri ve veri değerlerini inceleyebilirsiniz şekilde algoritmik kodu için kesme noktaları ayarlayın.  

4.  C veya C++ kodu, kod durdurmak için kullanım kesme noktaları bunu yazıyorsanız, bellekle ilgili hataları için hata ayıklama sırasında adres değerleri (NULL bakın) ve başvuru sayıları inceleyebilirsiniz.  

 Kesme noktaları kullanma hakkında daha fazla bilgi için okuma [kullanarak kesme noktaları](../debugger/using-breakpoints.md)  

### <a name="setting-conditional-breakpoints"></a>Koşullu kesme noktalarını ayarlama  
 Döngü veya özyineleme bir kesme noktası varsa veya çok sık adım adım kesme noktalarını varsa, yalnızca belirli koşullar karşılandığında, kodunuzu askıya emin olmak için koşullu bir kesme noktası kullanın. Aksi takdirde, F11 awful çok tuşuna basarak.  

 Koşullu kesme noktası ayarlayın ve bir değişkeni belirli bir değere ayarlayın veya belirli bir eşiği geçirir kodunuzu askıya alma, bir kesme noktası ayarlamak için kenar boşluğunda'ı tıklatın ve ardından "dişlisine" vurgulu menüsünden seçmek için.  

 ![Visual Studio kesme noktası ayarları](../ide/media/vs_ide_gs_debug_breakpoint_settings.png "Vs_ide_gs_debug_breakpoint_settings")  

 Şuna benzer bir iletişim kutusu görürsünüz kesmenin için belirli koşullar ayarlayabileceğiniz.  

 ![Visual Studio koşullu kesme noktası](../ide/media/vs_ide_gs_debug_breakpoint_conditional.PNG "Vs_ide_gs_debug_breakpoint_conditional")  

 Koşullu kesme noktaları değerlendirmek için kullanılan ifadeleri bildirme konusunda daha fazla ayrıntı için Channel9 video çıkış denetleyin [Visual Studio'da kesme noktası yapılandırma deneyimi](http://channel9.msdn.com/Events/Visual-Studio/Connect-event-2014/711).  

### <a name="inspecting-your-code-at-run-time"></a>Kodunuzu çalışma zamanında inceleniyor  
 Çalışan kodunuzu bir kesme noktası ve durur geldiğinde değişkenlerinizi inceleyebilir ve çağrı yığınları neler olduğunu belirlemek için. Değerleri görmeyi beklediğiniz aralıklardaki misiniz? Çağrılar doğru sırayla yapılır?  

 ![Visual Studio çalışma &#45; saat değeri denetleme](../ide/media/vs_ide_gs_debug_inspect_value.PNG "vs_ide_gs_debug_inspect_value")  

 Şu anda içeren alanlara ve değerleri görmek için bir değişken gelin. Beklemediğiniz bir değer görürseniz, önceki veya arama kod satırıyla, büyük olasılıkla bir hata bulunmaktadır. Kesme noktaları Yukarı Taşı veya daha fazla aramanızı daraltmak için varolan kesme noktaları için koşullar ekleyebilirsiniz.  

 Ayrıca, Visual Studio Burada, uygulamanızın CPU ve bellek kullanımı zamanla inceleyebileceğiniz tanılama araçları penceresini görüntüler. Bunları beklenmeyen yoğun CPU kullanımı veya bellek ayırma için aramak için kullanın. İle birlikte kullanmak **izleme** penceresini açın ve ne beklenmeyen ağır kullanımı veya yayımlanmamış kaynakları neden olduğunu belirlemek için kesme noktaları.  

 ![Visual Studio tanılama araçları penceresindeki](../ide/media/vs_ide_gs_debug_diagnostic_tools.PNG "Vs_ide_gs_debug_diagnostic_tools")  

### <a name="running-unit-tests"></a>Birim testleri çalıştırma  
 Birim testleri, uygulama veya hizmet kod yollarının çalışma programlardır. Visual Studio hem yönetilen hem de yerel kod için Microsoft birim test çerçevelerini yükler. Birim testleri oluşturmak, bunları çalıştırmak ve sonuçları bu testler, rapor için bir birim testi çerçevesi kullanın. Kodunuzun doğru şekilde çalışıp çalışmadığını sınamak için değişiklik yaptığınız zaman yeniden çalıştır birim testleri. Visual Studio Enterprise edition kullandığınızda, her yapıdan sonra otomatik olarak testleri çalıştırabilirsiniz.  

 Başlamak için okuma [Intellitest ile kodunuz için birim testleri oluşturmak](../test/generate-unit-tests-for-your-code-with-intellitest.md).  

 Visual Studio ve nasıl bunlar daha iyi kalite kod oluşturmanıza yardımcı olabilir birim testleri hakkında daha fazla bilgi için okuma [birim testi Temelleri](../test/unit-test-basics.md).  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)   
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [64 Bit uygulamalarda hata ayıklama](../debugger/debug-64-bit-applications.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)