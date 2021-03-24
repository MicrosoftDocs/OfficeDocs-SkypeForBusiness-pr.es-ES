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
description: Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos que se emiten para instalar los informes en SQL Server Reporting Services.
ms.openlocfilehash: b861db053a8851b05ce72a08de6dfae39b9d3bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096856"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="7a1f6-103">SQL Server Reporting Services (invocar)</span><span class="sxs-lookup"><span data-stu-id="7a1f6-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="7a1f6-104">Después de proporcionar la información necesaria para la implementación de los informes del servidor de supervisión en Microsoft SQL Server 2008 R2 o Microsoft SQL Server Report Services de 2012, la página Ejecutar comandos muestra un resumen de los comandos que se emiten para instalar los informes en SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7a1f6-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="7a1f6-p101">Examine el resumen de los comandos y tenga en cuenta los mensajes de error o advertencia que se muestran. Si se genera un archivo de registro, selecciónelo en la lista desplegable de la ventana de resumen; a continuación, haga clic en **Ver registro** para ver en pantalla el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="7a1f6-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a1f6-107">Para que los informes de Reporting Services se implemente correctamente y para tener acceso a los informes una vez completada la implementación, debe tener abierto el puerto TCP/IP 80 (y opcionalmente, el puerto TCP 443 para SSL, si asigna un certificado a Reporting Services) en el Firewall de Windows con seguridad avanzada en el SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a1f6-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="7a1f6-108">Para obtener más información, consulta Configurar el Firewall de [Windows para permitir SQL Server acceso](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) para Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7a1f6-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="7a1f6-109">Después de revisar el resumen, haga clic en **Finalizar** para completar la instalación de los informes en el SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7a1f6-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
