---
title: 'Lync Server 2013: configuración de un nodo de monitor para ejecutar transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605a859717736785df2d726720c2984162ff830d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="3f623-102">Configuración de un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f623-102">Configuring a watcher node to run synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f623-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="3f623-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="3f623-p101">Después de instalar los archivos de agentes de System Center, configure el nodo de monitor. La configuración del nodo de monitor varía en función de si está dentro de la red del perímetro o fuera de dicha red.</span><span class="sxs-lookup"><span data-stu-id="3f623-p101">After the System Center agent files have been installed, you must next configure the watcher node itself. The steps you take to configure a watcher node will vary depending on whether your watcher node computer lies inside your perimeter network or outside your perimeter network.</span></span>

<span data-ttu-id="3f623-106">Cuando configure un nodo de monitor, elija también el tipo de método de autenticación que el nodo empleará.</span><span class="sxs-lookup"><span data-stu-id="3f623-106">When you configure a watcher node, you must also choose the type of authentication method to be employed by that node.</span></span> <span data-ttu-id="3f623-107">Lync Server 2013 permite elegir uno de estos dos métodos de autenticación: autenticación de servidor de confianza o de credenciales.</span><span class="sxs-lookup"><span data-stu-id="3f623-107">Lync Server 2013 enables you to choose one of two authentication methods: Trusted Server or Credential Authentication.</span></span> <span data-ttu-id="3f623-108">Las diferencias entre estos dos métodos se indican en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f623-108">The differences between these two methods are outlined in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f623-109">Configuración</span><span class="sxs-lookup"><span data-stu-id="3f623-109">Configuration</span></span></th>
<th><span data-ttu-id="3f623-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f623-110">Description</span></span></th>
<th><span data-ttu-id="3f623-111">Ubicaciones admitidas</span><span class="sxs-lookup"><span data-stu-id="3f623-111">Locations Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f623-112">Servidor de confianza</span><span class="sxs-lookup"><span data-stu-id="3f623-112">Trusted Server</span></span></p></td>
<td><p><span data-ttu-id="3f623-113">Usa un certificado para representar a un servidor interno y evitar los problemas de autenticación.</span><span class="sxs-lookup"><span data-stu-id="3f623-113">Uses a certificate to impersonate an internal server and bypass authentication challenges.</span></span></p>
<p><span data-ttu-id="3f623-114">Es útil para los administradores que prefieran administrar un solo certificado en vez de varias contraseñas de usuario en cada nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="3f623-114">This is useful for administrators who would prefer to manage a single certificate instead of many user passwords on each watcher node.</span></span></p></td>
<td><p><span data-ttu-id="3f623-115">Dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="3f623-115">Inside the enterprise.</span></span></p>
<p><span data-ttu-id="3f623-p103">Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se están supervisando. Si están en dominios diferentes, use la autenticación de credenciales.</span><span class="sxs-lookup"><span data-stu-id="3f623-p103">Note that, with this method, the watcher node must be in the same domain as the pools being monitored. If the watcher node and the monitored pools are in different domains, use Credential Authentication instead.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f623-118">Autenticación de credenciales</span><span class="sxs-lookup"><span data-stu-id="3f623-118">Credential Authentication</span></span></p></td>
<td><p><span data-ttu-id="3f623-119">Almacena los nombres de usuario y las contraseñas con seguridad en Windows Credential Manager en cada nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="3f623-119">Stores user names and passwords securely in Windows Credential Manager on each watcher node.</span></span></p>
<p><span data-ttu-id="3f623-p104">Este modo necesita más administración de contraseñas, pero es la única opción para los nodos de monitor ubicados fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3f623-p104">This mode requires more password management, but is the only option for watcher nodes located outside of the enterprise. These watcher nodes cannot be treated as an endpoint trusted for authentication.</span></span></p></td>
<td><p><span data-ttu-id="3f623-122">Fuera de la empresa.</span><span class="sxs-lookup"><span data-stu-id="3f623-122">Outside the enterprise.</span></span></p>
<p><span data-ttu-id="3f623-123">Dentro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="3f623-123">Inside the enterprise.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f623-124">También debe comprobar que el firewall tiene reglas de entrada para MonitoringHost. exe y PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="3f623-124">You should also verify that your firewall has inbound rules for both MonitoringHost.exe and PowerShell.exe.</span></span> <span data-ttu-id="3f623-125">Si el Firewall bloquea estos procesos, se producirá un error de 504 (tiempo de espera de servidor) en las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="3f623-125">If these processes are blocked by the firewall then your synthetic transactions will fail with a 504 (server timeout) error.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

