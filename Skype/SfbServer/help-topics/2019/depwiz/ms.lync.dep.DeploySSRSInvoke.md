---
title: SQL Server Reporting Services (invocar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos que se emiten para instalar los informes en SQL Server Reporting Services.
ms.openlocfilehash: 17824f79ab0d710d4969d736b864912b424abaa9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109666"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="c1395-103">SQL Server Reporting Services (invocar)</span><span class="sxs-lookup"><span data-stu-id="c1395-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="c1395-104">Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server Report Services, la página Ejecutar comandos muestra un resumen de los comandos emitidos para instalar los informes en SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c1395-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="c1395-p101">Examine el resumen de los comandos y tenga en cuenta los mensajes de error o advertencia que se muestran. Si se genera un archivo de registro, selecciónelo en la lista desplegable de la ventana de resumen; a continuación, haga clic en **Ver registro** para ver en pantalla el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="c1395-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c1395-107">Para que los informes de Reporting Services se implemente correctamente y para tener acceso a los informes una vez completada la implementación, debe tener abierto el puerto TCP/IP 80 (y opcionalmente, el puerto TCP 443 para SSL, si asigna un certificado a Reporting Services) en el Firewall de Windows con seguridad avanzada en el SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c1395-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="c1395-108">Para obtener más información, consulta Configurar el Firewall de [Windows para permitir SQL Server acceso](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) para Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="c1395-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="c1395-109">Después de revisar el resumen, haga clic en **Finalizar** para completar la instalación de los informes en el SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="c1395-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
