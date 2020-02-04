---
title: 'Lync Server 2013: documentación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Documentation
ms:assetid: 5a69c0a2-0986-49c3-809c-89bc175a34ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720335(v=OCS.15)
ms:contentKeyID: 63969609
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eaeb06f1d9144d0c6f28984d509b3777673e10f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="d9c31-102">Documentación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9c31-102">Documentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9c31-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="d9c31-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="d9c31-104">El modelo de MOF se compone de numerosas funciones de administración de servicios.</span><span class="sxs-lookup"><span data-stu-id="d9c31-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="d9c31-105">La documentación sobre cómo y cuándo se realizan las tareas puede compartirse con miembros del mismo equipo o con otros equipos.</span><span class="sxs-lookup"><span data-stu-id="d9c31-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="d9c31-106">El método de almacenar y compartir la documentación puede variar según el tipo de función.</span><span class="sxs-lookup"><span data-stu-id="d9c31-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="d9c31-107">Por ejemplo, los procedimientos para la administración del sistema se pueden almacenar como documentos de Word porque es probable que se impriman y hagan referencia a ellos con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d9c31-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="d9c31-108">La información de administración de configuración puede generarse automáticamente y almacenarse en una base de datos para facilitar la búsqueda y la indización.</span><span class="sxs-lookup"><span data-stu-id="d9c31-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="d9c31-109">Puede que la documentación sea delicada y se debe restringir.</span><span class="sxs-lookup"><span data-stu-id="d9c31-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="d9c31-110">Sistemas de administración de documentos</span><span class="sxs-lookup"><span data-stu-id="d9c31-110">Document management systems</span></span>

<span data-ttu-id="d9c31-111">Un sistema de administración de documentación actúa como un repositorio central para los documentos y ayuda a garantizar que solo esté disponible la última revisión de un documento.</span><span class="sxs-lookup"><span data-stu-id="d9c31-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="d9c31-112">También puede considerar el archivado de la versión anterior del documento como referencia.</span><span class="sxs-lookup"><span data-stu-id="d9c31-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="d9c31-113">Lync Server proporciona una funcionalidad adecuada para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="d9c31-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="d9c31-114">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="d9c31-114">Databases</span></span>

<span data-ttu-id="d9c31-115">Se han tratado varias funciones de administración y herramientas que son adecuadas para usar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d9c31-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="d9c31-116">Es probable que el proceso de administración de la configuración utilice procesos automatizados que almacenan grandes cantidades de datos que requieren indización y búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d9c31-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="d9c31-117">El personal de soporte técnico puede buscar una base de datos de problemas y soluciones anteriores al solucionar problemas nuevos.</span><span class="sxs-lookup"><span data-stu-id="d9c31-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="d9c31-118">Es probable que se usen diferentes bases de datos para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="d9c31-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="d9c31-119">Decida si estas bases de datos se deben vincular o combinar.</span><span class="sxs-lookup"><span data-stu-id="d9c31-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="d9c31-120">Por ejemplo, si el servicio de asistencia al cliente identifica varios problemas con un tema común (como software nuevo que causa un problema con un determinado adaptador de red), el personal de soporte técnico puede consultar a la base de datos de configuración para predecir cuántos equipos pueden verse afectados.</span><span class="sxs-lookup"><span data-stu-id="d9c31-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

