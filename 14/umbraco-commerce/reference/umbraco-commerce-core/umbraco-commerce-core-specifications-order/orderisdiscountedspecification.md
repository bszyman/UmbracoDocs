---
title: OrderIsDiscountedSpecification
description: API reference for OrderIsDiscountedSpecification in Umbraco Commerce
---
## OrderIsDiscountedSpecification

```csharp
public class OrderIsDiscountedSpecification : IQuerySpecification<OrderReadOnly>, 
    ISpecification<OrderReadOnly>
```

**Inheritance**

* interface [IQuerySpecification&lt;!0&gt;](../../umbraco-commerce-common/umbraco-commerce-common-specifications/iqueryspecification-1.md)
* interface [ISpecification&lt;!0&gt;](../../umbraco-commerce-common/umbraco-commerce-common-specifications/ispecification-1.md)

**Namespace**
* [Umbraco.Commerce.Core.Specifications.Order](README.md)

### Constructors

#### OrderIsDiscountedSpecification (1 of 2)

```csharp
public OrderIsDiscountedSpecification(Guid discountId)
```

---

#### OrderIsDiscountedSpecification (2 of 2)

```csharp
public OrderIsDiscountedSpecification(IEnumerable<Guid> discountIds)
```


### Properties

#### DiscountIds

```csharp
public IEnumerable<Guid> DiscountIds { get; }
```


### Methods

#### Accept

```csharp
public void Accept(IVisitor visitor)
```


---

#### IsSatisfiedBy

```csharp
public bool IsSatisfiedBy(OrderReadOnly item)
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Core.dll -->