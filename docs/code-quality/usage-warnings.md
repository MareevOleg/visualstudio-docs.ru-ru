---
title: "Предупреждения использования | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.usagerules"
helpviewer_keywords: 
  - "предупреждения, использование"
  - "предупреждения при анализе управляемого кода, предупреждения использования"
  - "предупреждения использования"
ms.assetid: fe7dc2a3-289d-4bf7-a1e4-0947a81287c4
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 24
---
# Предупреждения использования
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Предупреждения использования поддерживают правильное использование платформы .NET Framework.  
  
## В этом подразделе  
  
|Правило|Описание|  
|-------------|--------------|  
|[CA1801: проверьте неиспользуемые параметры](../Topic/CA1801:%20Review%20unused%20parameters.md)|Сигнатура метода включает параметр, не использующийся в основной части метода.|  
|[CA1806: не игнорируйте результаты метода](../code-quality/ca1806-do-not-ignore-method-results.md)|Создается, но никогда не используется новый объект, либо вызывается метод, который создает и возвращает новую строку, и такая новая строка никогда не используется, либо метод COM или P\/Invoke возвращает HRESULT или код ошибки, который никогда не используется.|  
|[CA1816: вызов GC.SuppressFinalize должен осуществляться правильно](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Метод, являющийся реализацией Dispose, не вызывает GC.SuppressFinalize, либо метод, не являющийся реализацией Dispose, вызывает GC.SuppressFinalize, либо метод вызывает GC.SuppressFinalize и передает что\-либо другое \(Me в Visual Basic\).|  
|[CA2200: следует повторно вызывать исключение для сохранения сведений о стеке](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|В операторе throw повторно создается и явным образом задается исключение.  Если исключение повторно создается заданием исключения в операторе throw, список вызовов метода между исходным методом, создавшим исключение, и текущим методом будет утерян.|  
|[CA2201: не вызывайте зарезервированные типы исключений](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|Из\-за этого становится трудно обнаружить и отладить изначальную ошибку.|  
|[CA2202: не удаляйте объекты несколько раз](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Реализация метода содержит пути кода, которые могли стать причиной многократного вызова метода System.IDisposable.Dispose или эквивалентного метода Dispose \(например, метода Close\(\) для некоторых типов\) для одного и того же объекта.|  
|[CA2204: литералы должны иметь правильное написание](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|Литеральная строка в теле метода содержит одно или несколько слов, не распознаваемых библиотекой системы проверки орфографии Майкрософт.|  
|[CA2205: используйте управляемые эквиваленты API Win32](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Определен метод вызова неуправляемого кода, при этом в библиотеке классов .NET Framework существует метод с эквивалентной функциональностью.|  
|[CA2207: инициализируйте статические поля типа значений встроенными средствами](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Тип значения объявляет явный статический конструктор.  Чтобы устранить нарушение данного правила, выполните инициализацию всех статических данных при их объявлении и удалите статический конструктор.|  
|[CA2208: правильно создавайте экземпляры аргументов исключений](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|Вызывается конструктор по умолчанию \(без параметров\), принадлежащий к типу исключения ArgumentException или унаследованный от него, или неправильный аргумент строки передается параметризованному конструктору, принадлежащему к типу исключения ArgumentException или унаследованному от него.|  
|[CA2211: неконстантные поля должны быть скрыты](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|Для статических полей, которые не являются константными и доступными только для чтения, невозможно обеспечить потокобезопасность.  Доступ к подобным полям должен тщательно контролироваться, и для синхронизации доступа к такому объекту класса требуются дополнительные методы программирования.|  
|[CA2212: не следует помечать обслуживаемые компоненты атрибутом WebMethod](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|Метод в типе, унаследованном от System.EnterpriseServices.ServicedComponent, помечен атрибутом System.Web.Services.WebMethodAttribute.  Так как атрибут WebMethodAttribute и метод ServicedComponent имеют разное поведение и предъявляют конфликтующие требования к контексту и потоку транзакций, в некоторых сценариях поведение метода будет неправильным.|  
|[CA2213: следует высвобождать высвобождаемые поля](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Тип, реализующий System.IDisposable, объявляет поля, принадлежащие к типам, которые также реализуют IDisposable.  Метод Dispose поля не вызывается методом Dispose объявляющего типа.|  
|[CA2214: не вызывайте переопределяемые методы в конструкторах](../Topic/CA2214:%20Do%20not%20call%20overridable%20methods%20in%20constructors.md)|Когда конструктор вызывает виртуальный метод, возможна ситуация, когда конструктор для экземпляра, вызывающего метод, не выполняется.|  
|[CA2215: методы Dispose должны вызывать такие же методы базового класса](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Если тип наследуется от удаляемого типа, он должен вызвать метод Dispose базового типа из собственного метода Dispose.|  
|[CA2216: высвобождаемые типы должны объявлять метод завершения](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|Тип, который реализует System.IDisposable и имеет поля, предусматривающие использование неуправляемых ресурсов, не реализует метод завершения, как описано в Object.Finalize.|  
|[CA2217: не следует помечать перечисления атрибутом FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|Доступное для внешнего кода перечисление помечено атрибутом FlagsAttribute и имеет одно или несколько значений, которые не являются числа два или сочетанием других определенных значений в перечислении.|  
|[CA2218: переопределяйте GetHashCode при переопределении Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode возвращает значение на основе текущего экземпляра, используемое для алгоритмов хэширования и структур данных, таких как хэш\-таблица.  Два равных объекта, принадлежащие к одному и тому же типу, должны возвращать один и тот же хэш\-код.|  
|[CA2219: не создавайте исключения в предложениях исключений](../Topic/CA2219:%20Do%20not%20raise%20exceptions%20in%20exception%20clauses.md)|Если исключение создается в предложении finally или fault, новое исключение скрывает активное исключение.  Если исключение создается в предложении filter, среда выполнения перехватывает исключение без оповещения.  Из\-за этого становится трудно обнаружить и отладить изначальную ошибку.|  
|[CA2220: методы завершения должны вызывать метод завершения базового класса](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|Финализация должна распространятся посредством иерархии наследования.  Для этого типы должны вызывать свой метод Finalize базового класса из собственного метода Finalize.|  
|[CA2221: методы завершения должны быть защищены](../code-quality/ca2221-finalizers-should-be-protected.md)|В методах завершения должен использоваться модификатор доступа из семейства.|  
|[CA2222: не уменьшайте видимость унаследованных членов](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Не следует изменять модификатор доступа для унаследованных членов.  Если сделать унаследованный член закрытым, то доступ вызывающих объектов к реализации метода базового класса все равно не будет запрещен.|  
|[CA2223: члены должны различаться не только возвращаемым типом](../Topic/CA2223:%20Members%20should%20differ%20by%20more%20than%20return%20type.md)|Среда CLR позволяет использовать возвращаемые типы для различения совпадающих в остальном членов, однако эта функция не входит в спецификацию CLS и поддерживается не всеми языками программирования .NET.|  
|[CA2224: переопределяйте равенство при перегрузке оператора равенства](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Открытый тип реализует оператор равенства, но не переопределяет Object.Equals.|  
|[CA2225: для перезагрузок оператора существуют дополнения с именами](../Topic/CA2225:%20Operator%20overloads%20have%20named%20alternates.md)|Обнаружена перегрузка оператора, однако не найден ожидаемый именованный альтернативный метод.  Именованный альтернативный член предоставляет те же функции, что и основной оператор, и его могут использовать разработчики, которые программируют на языках, не поддерживающих перегрузку операторов.|  
|[CA2226: перегрузки операторов должны быть симметричны](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|Тип реализует оператор равенства или неравенства, но не реализует противоположный оператор.|  
|[CA2227: свойства коллекции должны иметь параметр "только для чтения"](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Свойство коллекции, допускающее запись, позволяет пользователю заменять одну коллекцию другой.  Свойство только для чтения предотвращает замену коллекции, но по\-прежнему допускает установку, настройку отдельных членов.|  
|[CA2228: не следует поставлять невыпущенные форматы ресурсов](../Topic/CA2228:%20Do%20not%20ship%20unreleased%20resource%20formats.md)|Файлы ресурсов, созданные с помощью предварительных версий .NET Framework, могут не работать в поддерживаемых версиях платформы .NET Framework.|  
|[CA2229: применяйте конструкторы сериализации](../code-quality/ca2229-implement-serialization-constructors.md)|Чтобы устранить нарушение этого правила, реализуйте конструктор сериализации.  Для запечатанного класса конструктор должен быть закрытым, а в иных случаях — защищенным.|  
|[CA2230: используйте параметры для аргументов переменной](../code-quality/ca2230-use-params-for-variable-arguments.md)|Открытый или защищенный тип содержит открытый или защищенный метод, который использует соглашение о вызовах VarArgs вместо ключевого слова params.|  
|[CA2231: перегружать равенство операторов следует при перегрузке ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Тип значения переопределяет Object.Equals, но не реализует оператор равенства.|  
|[CA2232: отметьте точки входа Windows Forms меткой STAThread](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|Атрибут STAThreadAttribute указывает, что потоковой моделью COM для приложения является однопотоковое подразделение.  Данный атрибут должен находиться в точке входа любого приложения, использующего Windows Forms; если он отсутствует, компоненты Windows могут работать неправильно.|  
|[CA2233: в операциях не должно быть переполнений](../code-quality/ca2233-operations-should-not-overflow.md)|Прежде чем выполнять арифметические операции, необходимо проверить операнды и убедиться, что результат операции находится в диапазоне возможных значений для используемых типов данных.|  
|[CA2234: передавайте объекты System.Uri вместо строк](../Topic/CA2234:%20Pass%20System.Uri%20objects%20instead%20of%20strings.md)|Вызывается метод, имеющий параметр строки, имя которого содержит uri, URI, urn, URN, url или URL.  Объявляющий тип метода содержит соответствующую перегрузку метода, которая имеет параметр System.Uri.|  
|[CA2235: помечайте все несериализуемые поля](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Экземпляр поля несериализуемого типа объявлен в сериализуемом типе.|  
|[CA2236: вызывайте методы базового класса для типов ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|Чтобы устранить нарушение этого правила, вызовите метод базового типа GetObjectData или конструктор сериализации из соответствующего метода производного типа или конструктора.|  
|[CA2237: пометьте типы ISerializable атрибутом SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|Чтобы среда CLR распознавала тип как сериализуемый, он должен быть помечен атрибутом SerializableAttribute, даже если тип использует пользовательскую процедуру сериализации посредством реализации интерфейса ISerializable.|  
|[CA2238: следует правильно реализовывать методы сериализации](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Метод, обрабатывающий событие сериализации, не имеет правильной сигнатуры, возвращаемого типа или отображения.|  
|[CA2239: предоставляйте методы десериализации для необязательных полей](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|Тип имеет поле, помеченное атрибутом System.Runtime.Serialization.OptionalFieldAttribute, и не предоставляет методы обработки событий десериализации.|  
|[CA2240: правильно реализуйте ISerializable](../Topic/CA2240:%20Implement%20ISerializable%20correctly.md)|Чтобы устранить нарушение данного правила, сделайте метод GetObjectData доступным для внешнего кода и переопределяемым и убедитесь, что все поля экземпляра включены в процесс сериализации или явно помечены атрибутом NonSerializedAttribute.|  
|[CA2241: предоставьте правильные аргументы методам форматирования](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|Аргумент формата, переданный методу System.String.Format, не содержит элемент форматирования, соответствующий каждому аргументу объекта, или наоборот.|  
|[CA2242: правильно выполняйте проверку NaN](../code-quality/ca2242-test-for-nan-correctly.md)|Это выражение проверяет значение на соответствие Single.Nan или Double.Nan.  Используйте Single.IsNan\(Single\) или Double.IsNan\(Double\) для проверки значения.|  
|[CA2243: синтаксический анализ строковых литералов атрибута должен осуществляться правильно](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|Не удается правильно выполнить синтаксический анализ параметра строкового литерала атрибута для URL\-адреса, идентификатора GUID или версии.|