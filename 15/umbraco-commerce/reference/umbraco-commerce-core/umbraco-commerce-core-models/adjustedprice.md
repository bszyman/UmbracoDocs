---
title: AdjustedPrice
description: API reference for AdjustedPrice in Umbraco Commerce
---
## AdjustedPrice

```csharp
public class AdjustedPrice : IDeepCloneable
```

**Inheritance**

* interface [IDeepCloneable](../../umbraco-commerce-common/umbraco-commerce-common/ideepcloneable.md)

**Namespace**
* [Umbraco.Commerce.Core.Models](README.md)

### Properties

#### Adjustment

```csharp
public virtual Price Adjustment { get; set; }
```


---

#### Adjustments

```csharp
public virtual List<PriceAdjustment> Adjustments { get; }
```


---

#### Value

```csharp
public virtual Price Value { get; set; }
```


---

#### WithoutAdjustments

```csharp
public virtual Price WithoutAdjustments { get; set; }
```


### Methods

#### ZeroValue

```csharp
public static AdjustedPrice ZeroValue(Guid currencyId)
```


---

#### AsReadOnly

```csharp
public virtual ReadOnlyAdjustedPrice AsReadOnly()
```


---

#### DeepClone

```csharp
public virtual object DeepClone()
```


---

#### GetHashCode

```csharp
public override int GetHashCode()
```


---

#### ToString

```csharp
public override string ToString()
```


### Operators

#### AdjustedPrice Implicit (1 of 2)

```csharp
public static implicit operator Price(AdjustedPrice adjustedPrice)
```

---

#### AdjustedPrice Implicit (2 of 2)

```csharp
public static implicit operator decimal(AdjustedPrice adjustedPrice)
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Core.dll -->