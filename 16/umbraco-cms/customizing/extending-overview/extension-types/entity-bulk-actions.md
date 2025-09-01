---
description: Bulk Entity Actions perform an action on a selection of items.
---

# Entity Bulk Actions

Extension authors can register an entity bulk action to be available in the context menu of a collection. The manifest
passes control over to a custom `UmbEntityBulkActionBase` class that will be instantiated and executed when the action
is clicked. The class will have access to the host element, a repository with the given alias, and a selection of items
to perform the action on.

When the action is completed, an event on the host element will be dispatched to notify any surrounding elements.

<figure><img src="../../../.gitbook/assets/entity-bulk-action-collection-menu.svg" alt=""><figcaption><p>Entity Bulk Collection</p></figcaption></figure>

## Registering an Entity Bulk Action <a href="#registering-an-entity-bulk-action" id="registering-an-entity-bulk-action"></a>

```typescript
import { umbExtensionsRegistry } from '@umbraco-cms/backoffice/extension-registry';
import { MyEntityBulkAction } from './entity-bulk-action';

const manifest = {
 type: 'entityBulkAction',
 alias: 'My.EntityBulkAction',
 name: 'My Entity Bulk Action',
 weight: 10,
 api: MyEntityBulkAction,
 meta: {
  icon: 'icon-add',
  label: 'My Entity Bulk Action',
  repositoryAlias: 'My.Repository',
 },
 conditions: [
  {
   alias: 'Umb.Condition.CollectionAlias',
   match: 'my-collection-alias',
  },
 ],
};

umbExtensionsRegistry.register(manifest);
```

## The Entity Bulk Action Class <a href="#the-entity-bulk-action-class" id="the-entity-bulk-action-class"></a>

```typescript
import { UmbEntityBulkActionBase } from '@umbraco-cms/backoffice/entity-bulk-action';
import { UmbControllerHostElement } from '@umbraco-cms/backoffice/controller-api';
import { MyRepository } from './my-repository';

export class MyEntityBulkAction extends UmbEntityBulkActionBase<MyRepository> {
 constructor(host: UmbControllerHostElement, repositoryAlias: string, selection: Array<string>) {
  super(host, repositoryAlias, selection);
 }

 async execute() {
  await this.repository?.myBulkAction(this.selection);
 }
}
```
