---
Description: Associates settings data with a managed element.
ms.assetid: 3fdf111b-3ec1-4559-94ce-27d6a8cd0080
title: CIM\_SettingsDefineState class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CIM\_SettingsDefineState class

Associates settings data with a managed element.

## Syntax

``` syntax
[Association, Abstract, Version("2.22.0"), UMLPackagePath("CIM::Core::Settings")]
class CIM_SettingsDefineState
{
  CIM_ManagedElement REF ManagedElement;
  CIM_SettingData    REF SettingData;
};
```

## Members

The **CIM\_SettingsDefineState** class has these types of members:

-   [Properties](#properties)

### Properties

The **CIM\_SettingsDefineState** class has these properties.

<dl> <dt>

**ManagedElement**
</dt> <dd> <dl> <dt>

Data type: **CIM\_ManagedElement**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Key**](https://msdn.microsoft.com/library/aa392157)
</dt> </dl>

The managed element in the association.

</dd> <dt>

**SettingData**
</dt> <dd> <dl> <dt>

Data type: **CIM\_SettingData**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Key**](https://msdn.microsoft.com/library/aa392157)
</dt> </dl>

The settings data in the association.

</dd> </dl>

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1<br/>                                                                                  |
| Minimum supported server<br/> | Windows Server 2012 R2<br/>                                                                       |
| Namespace<br/>                | Root\\virtualization\\v2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



 

 



