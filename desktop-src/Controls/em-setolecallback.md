---
title: EM\_SETOLECALLBACK message
description: Gives a rich edit control an IRichEditOleCallback object that the control uses to get OLE-related resources and information from the client.
ms.assetid: bd1f8048-214c-4ac6-b826-bedabb1aaee5
keywords:
- EM_SETOLECALLBACK message Windows Controls
topic_type:
- apiref
api_name:
- EM_SETOLECALLBACK
api_location:
- Richedit.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# EM\_SETOLECALLBACK message

Gives a rich edit control an [**IRichEditOleCallback**](/windows/win32/Richole/nn-richole-iricheditolecallback?branch=master) object that the control uses to get OLE-related resources and information from the client.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

This parameter is not used; it must be zero.

</dd> <dt>

*lParam* 
</dt> <dd>

Pointer to an [**IRichEditOleCallback**](/windows/win32/Richole/nn-richole-iricheditolecallback?branch=master) object. The control calls the [**AddRef**](https://msdn.microsoft.com/library/windows/desktop/ms691379) method for the object before returning.

</dd> </dl>

## Return value

If the operation succeeds, the return value is a nonzero value.

If the operation fails, the return value is zero.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Richedit.h</dt> </dl> |



 

 




