# React-Props-ts-Lesson

# React.tsx
سوف نتعلم في هذا الدرس :


كيفية استخدام **TypeScript** مع React


تنزيل **TypeScript**


التعرف على الملفات بعد تنزيل مكتبة React


التعرف على props وكيفية التعامل معها 


ــــــــــــــــــــــــــــــــــــــــــــ

## 

يقدم  TypeScript دعمًا كاملاً لـ React و JSX. هذا يعني أنه يمكننا استخدام TypeScript مع إطار العمل React  .

لبدء إستخدام TypeScript مع React 
نقوم اولًا بإنشاء مجلد على سطح المكتب ونختار له الاسم المراد تسميته به في حالتنا هذه قمنا بإنشاء مجلد بالإسم React-TS
ثانيًا: سنقوم بفتح المجلد بمحرر الأكواد الخاص بنا VS ، والتحقق من مسار الملف ومن ثم كتابة الأمر التالي لتحميل المكتبة 


    npx create-react-app my-app --template typescript
    
    # or
    
    yarn create react-app my-app --template typescript

يسمح لنا  أمر (create-react-app) من انشاء ملفات مكتبة React بداخل المجلد  
لقد قمنا بتعيين الاسم my-app الى مشروعنا ويمكننا تغيره الى اي مسمى اخر بمعنى لو كان لدينا مشروع عبارة عن متجر فبإمكاننا تغير الاسم الى create-react-app store

*ملاحظة: لا يسمح بكتابة الحروف الكبيره عند انشاء مشروع React 


## مثال :
    npx create-react-app My-app --template typescript

يسمح لنا الأمر --template typescript بإستخدام typescript مع  React وبهذا نستطيع كتابة ملف بـ .ts

## الأمر npx :

في حال اردنا تشغيل اي مكتبة نقوم بإستخدام الأمر npx فهذا يسمح بتحميل جميع الملفات المعنية وتشغيلها مباشرة 

_____________________
سوف نلاحظ انه قم تم انشاء مجلد جديد بإسم my-app 

قبل تشغيل الملف سوف نتعرف على محتوياته اولًا 


- مجلد node_modules يحتوي على جميع المكاتب التي تم تنزيلها ونستطيع العمل معها .
- مجلد public يحتوي على ملف index.html حيث يقوم هذا الملف بربط مشروعنا مع document

<div id="root"></div>
ونلاحظ انه يحتوي على id التي بدورها تربطنا بملف index.tsx .
 يتم اضافة الصور الخاصة بالمشروع في مجلد public ويعود السبب ان المسار الخاص بالصوره عند وضعها في مجلد public يكون مفتوح ونستطيع الوصول اليه من المتصفح من خلال المسار الخاص بالصورة
 
 فمثلًا لو قمنا بنسخ المسار الخاص بصورة logo192 ووضعه في المتصفح ستكون الصورة مرئيه لنا .
 

- ملف  package.json يحتوي هذا الملف على جميع المكاتب اللي تم تحميلها لإستخدامها في المشروع ، فمثلًا حين نحاول تحميل مكتبة مثل axios فسيتم إضافة المكتبة في هذا الملف .

ويحتوي ايضاً على معلومات المشروع  مثل اسم المشروع ونسخته والإعتمادات اللي يعتمد عليها المشروع حتى يقوم بالتفاعل معنا 


- ملف package-lock.json : حين نقوم بتحميل مكتبة axios مثلًا فستذهب معلوماتها الى ملف package.json لكن جميع الحزم اللتي تم بناء حزمة axios بها والإعتمادات التي يعتمد عليها axios للتفاعل معنا سوف تكون مخزنة في هذا الملف .
- ملف tsconfig.json :  يحتوي على نسخة es المستخدمة وعلى مسا تشغيل الملف src
- ملف .gitignore : يحتوي على الملفات التي تريد من المشروع تجاهل تحميلها حين نقوم تنزيل المشروع على على github  مثل node_modules فحين محاولة تنزيله على github ستكون عملية ثقيلة وطويله وتسبب الضرر بالسيرفر الخاص بـgithub وايضًا الملفات التي تحتوي. على معلومات سرية او خاصة مثل الرقم السري الخاص بربط مشروعك بقاعدة البيانات .
- مجلد src : يحتوي هذا امجلد على الكثير من الملفات والتي نعتمد عليها لتشغيل المشروع :

                            ـ index.tsx لقد ذكرنا سابقًا انه تم ربط هذا الملف مع id الموجوده بملف index.html حتى نستطيع ربط مشروعنا مع document وتشغيله ، ويقوم ايضًا بمحاوطة ملف App  بإعتبارة الملف الاساسي للمشروع ونقوم من خلاله بتمرير الملفات الاخرى اليه حتى يقوم بقراءتها وتفعيلها مع المتصفح.
                            
                            -ملف App يعتبر الملف الرئيسي لتشغل المشروع والمسؤول عن عرض البيانات على الشاشة
                             نلاحظ انه تم كتابة اول حرف بشكل كبير حيث يمنع React كتابة اول حرف من  اسم        الـcomponnent بشكل صغير 
                             - ملف App.css ونستطيع من خلال هذا الملف اضافة التصميم الخاص بالمشروع 
                             ــــــــــــــــــــــ
        نلاحظ ان جميع الملفات تحمل في نهايتها على tsx وهذا يعني انها تعمل مع **TypeScript** 
        
        ــــــــــــــــــــ
        
        لنعود الى تشغيل المجلد ونلاحظ عند الإنتهاء من انشاء مجلد my-app  ظهور بعض الأوامر التي يجب تتبعها حتى نستطيع تشغيل المشروع 
        
        اولًا نقوم بالذهاب الى مسار المشروع وهو my-app عن طريق الأمر 

                          cd my-app

 وبعد التأكد من اننا في المسار الصحيح للمشروع نقوم بكتابة الأمر 

      npm start

بعدها سوف نلاحظ ظهور شاشة جديده على المتصفح ، هذا يعني انه تم تشغيل المشروع بنجاح .

بعدها نلاحظ وجود بيانات على الشاشه مثل الأيقونه ولون الخلفيه وجملة “Edit `src/App.tsx` and save to reload.”
 لكن من اين جاءت هذه البيانات ؟ كما ذكرنا سابقًا ان ملف App يحتوي على المكونات المراد عرضها لذا اذا ذهبنا الى App سوف نجد ان جميع البيانات المعروضه موجوده فيه .
 لذا اذا قمنا بحذف المحتويات بدايةً من <header>  الى نهايته <header/> وعند العودة الى المتصفح نجد انها اصبحت بيضاء بعد حذف معلوماتها .
 
 لنحاول مثلًا كتابة نص بالداخل <div> Hello World</div>
 بعدها نعود الى المتصفح ونلاحظ ظهور النص على الشاشة .
 
 لكن ماذا لو ازلنا <div></div> وقمنا بكتبة النص مباشرة داخل <h1> ؟
 نلاحظ انه سيسمح لنا بكتابة نص واحد فقط لكن لو اضفنا اكثر من نص او اي عنصر اخر فستظهر لنا رسالة الخطأ 
 ويعود السبب الى ان return يسمح بشتغيل عنصر واحد فقط لذا وتفاديًا لحدوث اي خطأ نقوم بوضع جميع المحتويات بداخل <div></div> لأنه بدوره يسمح لنا بكتابة أكثر من عنصر بداخله 
 
 _____________

#  التعامل مع React props with TypeScript

 

## ماهو مفهوم props ؟

تستخدم **props** لتخزين البيانات التي يمكن لأبناء مكون React الوصول إليها.
هي جزء من مفهوم إعادة الاستخدام. تحل props محل محل class attributes وتسمح لك بإنشاء واجهات متسقة عبر التسلسل الهرمي للمكونات.


## ماهي props في React ؟

ببساطه props هي مفهوم لـproperties وهو ما يجعل المكونات قابلة لإعادة الاستخدام. لأنه يؤدي وظيفة أساسية - يقوم بتمرير البيانات من مكون إلى آخر.
تعمل props كقناة اتصال للمكونات. يتم تمرير props من الوالد إلى الطفل وتساعد طفلك على الوصول إلى الخصائص التي جعلته في شجرة الوالدين.
الآن ، تخيل أن لدينا مكونًا في شكل منتج يتكون من اسم المنتج ووصفه وسعره. كل ما يتعين علينا القيام به هو كتابة المكون مرة واحدة وإعادة استخدامه عدة مرات عن طريق تغيير البيانات التي نمررها عبر props .


- نستطيع استخدام props في functional and class-based components
- نقوم بتمرير props من الأعلى إلى الأسفل ، يمكننا أيضًا أن نشير إليها على أنها سلف لأحفاد ، أو من والد إلى طفل.
- تُستخدم props للقراءة فقط ،هذا يعني أنه بمجرد أن يتلقى المكون مجموعة من الخصائص ، لا يمكننا تغييره ، لكن يمكننا فقط استخدامه واستهلاكه ولا يمكننا تعديل الخصائص التي تم تمريرها إلى المكون. إذا أردنا تعديل ذلك ، فسيتعين علينا تقديم ما نسميه  state in React.



## كيف يتم استخدام React props with TypeScript

لنفترض ان لدينا منتج كـcomponent ونريد اعادة استخدامة .
لكن اولًا علينا التعلم كيفية استخدام props بدون تدميرها ، تعتبر معرفة كيفية استخدام props دون إتلافها أمرًا ضروريًا كمبتدئ حتى تتمكن من فهم فكرة كيفية عمل props.

اولًا سنقوم بإنشاء مجلد ونطلق عليه اسم component وبداخل المجلد نقوم بإنشاء ملف ونطلق عليه الأسم المناسب في حالتنا هذه سنقوم بتسميته MyProducts ونلاحظ انه تم كتابة اول حرف بشكل كبير ، بعد الانتهاء من انشاء الملف نقوم بكتابة محتواه بإستخدام functiona 

*ملاحظه: سوف نقوم بالتعامل مع  functional component خلال هذا المسار .

يمكننا كتابة البنية الأساسيه للمكون عن طريق مساعدة محرر الأكواد vs extensions وتحميل  react E7 لمساعدتنا في كتابة الاختصارات 
سنقوم الان بكتابة الاحرف rfc او rfce  لإنشاء  functional component.


    import React from "react";
     
    function MyProducts() {
      return (
        <div>
      
        </div>
      );
    }
     
    export default MyProducts;

سابقًا وبإستخدام React فقط كنا نقوم بتمرير props بداخل function كـ**Parameter  وهو عبارة عن**  متغير يتم تعريفه بين أقواس الدالة. ومن ثم تمريره بداخل JSX وارسال قيمته له .


    import React from "react";
     
    function MyProducts(props) {
      return (
        <div>
          <h1>{props.name}</h1>
          <p>{props.description}</p>
          <p>{props.price}</p>
        </div>
      );
    }
     
    export default MyProducts;

كما نلاحظ قمنا بتمرير props بداخل الدالة ومن ثم قم بإعطائها القيم المراده ونلاحظ ايضًا اننا قمنا بكتابتها بداخل اقواس object وهذا لأنها عبارة عن JavaScript وليست عناصر HTML ولكن بكتابتها داخل  <div> اصبحت JSX

لكن في حين اننا نتعامل مع TypeScript فلن يُسمح لنا بكتابتها بهذه الطريقه ويجب علينا اولًا تمرير النوع او واجهه لها 


## مثال :
    import React from "react";
     interface MyProductsProps {
    //سوف نقوم بتمرير كل المدخلات التي نريد تمريرها من خلال props بداخل الواجهه
       name:string; // لقد مررنا نوع المدخل الذي سوف يستقبله الاسم 
       description:string;
       price:number;
    
    }
    
    // سوف نقوم بتمرير اسم الواجهه بجانب props من خلال props:GreetProps حتى يتم التعرف عليها 
    function MyProducts(props:GreetProps) {
      return (
        <div>
    
          <h1>{props.name}</h1>
          <p>{props.description}</p>
          <p>{props.price}</p>
        </div>
      );
    }
     
    export default MyProducts;

الأن وبما اننا انتهينا من انشاء المكون سوف نذهب إلى App.js ونقوم بتمرير اسم المكون والمسار الخاص به في الأعلى حتى يستطيع التعرف عليه وعرض بياناته 


    import "./App.css";
    import MyProducts from "./component/MyProducts";
    function App() {
      return (
        <div className="App">
          <MyProducts
            name="MyStore"
            description="the product has fantastic features"
            price={1000}
          />
        </div>
      );
    }
     
    export default App;

كما نلاحظ اننا قمنا بتمرير مواصفات المنتج بداخل المكون وعند تشغيل المشروع والذهاب الى المتصفح سوف نرى البيانات معروضه .

إذن ، هذا هو منطق استخدام props. كان علينا أولاً أن نهيئها ، ثم احتجنا للوصول إلى props ونوع الخاصية التي تحملها. ثم تستهلك المكونات التي نقدمها تلك الخصائص وتمرر البيانات إليها.
تُعتبر props سهلة الإستخدام ويعود ذالك الى اننا نستطيع اعادة استخدام المكون لأكثر من مرة وبطرق مختلفة .


## مثال :
     import "./App.css";
    import MyProducts from "./component/MyProducts";
    function App() {
      return (
        <div className="App">
          <MyProducts
            name="MyStore"
            description="the product has fantastic features"
            price={1000}
          />
       <MyProducts
            name="iphone"
            description="awesome camera features!"
            price={5000}
          />
        </div>
      );
    }
     
    export default App;

نلاحظ اننا اعدنا كتابة المكون لكن ببيانات مختلفه وحين الذهاب الى المتصفح نجد انه تم عرض جميع البيانات ، لذا يمكنك أن ترى أننا نعيد استخدام نفس المكون بخصائص مختلفة.

وبهذا نستنتج ان التعامل مع props سهل ويمكننا اعادة استخدام المكون اكثر مره ولكن لا يمكننا التغيير عليه حيث ان قيمته تُعتبر قيمة ثابته .

