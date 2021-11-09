---
title: SQL Server Reporting Services (invocar)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos emitidos para instalar los informes en el SQL Server Reporting Services.
ms.openlocfilehash: 47b18c53dc936916d827ab12915ea423e7adc44a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838862"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services (invocar)
 
Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos emitidos para instalar los informes en el SQL Server Reporting Services.
  
Examine el resumen de los comandos y tenga en cuenta los mensajes de error o advertencia que se muestran. Si se genera un archivo de registro, selecciónelo en la lista desplegable de la ventana de resumen; a continuación, haga clic en **Ver registro** para ver en pantalla el archivo de registro.
  
> [!IMPORTANT]
> Para que los informes de Reporting Services se implemente correctamente y accedan a los informes una vez completada la implementación, debe tener abierto el puerto TCP/IP 80 (y opcionalmente, el puerto TCP 443 para SSL, si asigna un certificado a Reporting Services) en el Firewall de Windows con seguridad avanzada en el SQL Server. Para obtener más información, vea [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.
  
Después de revisar el resumen, haga clic en **Finalizar** para completar la instalación de los informes en el SQL Server Reporting Services.
