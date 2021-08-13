---
title: SQL Server Reporting Services (invocar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos emitidos para instalar los informes en el SQL Server Reporting Services.
ms.openlocfilehash: b16d9e521fc0f876a0d5132948a12ab821beff7b90a22314e78b2621dd995a6d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330184"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services (invocar)
 
Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos emitidos para instalar los informes en el SQL Server Reporting Services.
  
Examine el resumen de los comandos y tenga en cuenta los mensajes de error o advertencia que se muestran. Si se genera un archivo de registro, selecciónelo en la lista desplegable de la ventana de resumen; a continuación, haga clic en **Ver registro** para ver en pantalla el archivo de registro.
  
> [!IMPORTANT]
> Para que los informes de Reporting Services se implemente correctamente y accedan a los informes una vez completada la implementación, debe tener abierto el puerto TCP/IP 80 (y opcionalmente, el puerto TCP 443 para SSL, si asigna un certificado a Reporting Services) en el Firewall de Windows con seguridad avanzada en el SQL Server. Para obtener más información, vea [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.
  
Después de revisar el resumen, haga clic en **Finalizar** para completar la instalación de los informes en el SQL Server Reporting Services.
