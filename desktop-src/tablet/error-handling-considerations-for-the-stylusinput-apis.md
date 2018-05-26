---
Description: Overview of error handling when using the StylusInput application programming interfaces (APIs).
ms.assetid: 7d7ff5b2-3eda-4570-96fe-b3b8f41ff69b
title: Error Handling Considerations for the StylusInput API
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Error Handling Considerations for the StylusInput API

Unhandled exceptions thrown by a plug-in are caught by the [**RealTimeStylus**](/windows/win32/RTSCom/?branch=master) object. When a plug-in throws an exception, the normal flow of data is interrupted. The **RealTimeStylus** object:

1.  Creates an [ErrorData](T:Microsoft.StylusInput.PluginData.ErrorData) object (in managed code).
2.  Calls the [**Error**](/windows/win32/RTSCom/nf-rtscom-istylusplugin-error?branch=master) method (in managed code, either the [Microsoft.StylusInput.IStylusSyncPlugin.Error](frlrfMicrosoftStylusInputIStylusSyncPluginClassErrorTopic) or [Microsoft.StylusInput.IStylusAsyncPlugin.Error](frlrfMicrosoftStylusInputIStylusAsyncPluginClassErrorTopic) method) of the plug-in that threw the exception.
3.  Calls the [**Error**](/windows/win32/RTSCom/nf-rtscom-istylusplugin-error?branch=master) method of the remaining plug-ins in that collection.
4.  If the plug-in that threw the exception is a synchronous plug-in, the [ErrorData](T:Microsoft.StylusInput.PluginData.ErrorData) object (in managed code) is added to the output queue.
5.  The [**RealTimeStylus**](/windows/win32/RTSCom/?branch=master) object resumes normal processing of the original data.

If a plug-in throws an exception from its [**Error**](/windows/win32/RTSCom/nf-rtscom-istylusplugin-error?branch=master) method, the [**RealTimeStylus**](/windows/win32/RTSCom/?branch=master) object catches the exception but does not generate a new [ErrorData](T:Microsoft.StylusInput.PluginData.ErrorData) object. For more information about how ErrorData is added to the queue, see [Plug-in Data and the RealTimeStylus Class](plug-in-data-and-the-realtimestylus-class.md).

The [**RealTimeStylus**](/windows/win32/RTSCom/?branch=master) object does not stop processing data from the tablet pen's data stream when one of its plug-ins throws an exception. Depending on your design, some of your plug-ins may need to subscribe to the [ErrorData](T:Microsoft.StylusInput.PluginData.ErrorData) notification and modify their behavior when an exception occurs.

 

 


