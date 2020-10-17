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
ms.openlocfilehash: 2785391f93f2844809aaad06e4efff9c2e86505d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501177"
---
# <a name="documentation-in-lync-server-2013"></a><span data-ttu-id="a73a0-102">Documentación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a73a0-102">Documentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a73a0-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a73a0-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a73a0-104">El modelo de MOF se compone de muchas funciones de administración de servicios.</span><span class="sxs-lookup"><span data-stu-id="a73a0-104">The MOF model is composed of many service management functions.</span></span> <span data-ttu-id="a73a0-105">La documentación sobre cómo y cuándo se realizan las tareas se puede compartir con los miembros del mismo equipo o con otros equipos.</span><span class="sxs-lookup"><span data-stu-id="a73a0-105">Documentation about how and when tasks are performed can be shared with members of the same team or with other teams.</span></span> <span data-ttu-id="a73a0-106">El método de almacenamiento y uso compartido de la documentación puede variar según el tipo de función.</span><span class="sxs-lookup"><span data-stu-id="a73a0-106">The method of storing and sharing documentation can vary according to the type of function.</span></span> <span data-ttu-id="a73a0-107">Por ejemplo, los procedimientos para la administración del sistema pueden almacenarse como documentos de Word porque es probable que se impriman y hagan referencia a ellos con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a73a0-107">For example, the procedures for system administration may be stored as Word documents because they are likely to be printed and referenced frequently.</span></span> <span data-ttu-id="a73a0-108">La información de administración de configuración se puede generar automáticamente y almacenar en una base de datos para facilitar la búsqueda y la indización.</span><span class="sxs-lookup"><span data-stu-id="a73a0-108">Configuration management information may be automatically generated and stored in a database for easy searching and indexing.</span></span> <span data-ttu-id="a73a0-109">Algunos documentos pueden ser confidenciales y deben restringirse.</span><span class="sxs-lookup"><span data-stu-id="a73a0-109">Some documentation may be sensitive and should be restricted.</span></span>

<div>

## <a name="document-management-systems"></a><span data-ttu-id="a73a0-110">Sistemas de administración de documentos</span><span class="sxs-lookup"><span data-stu-id="a73a0-110">Document management systems</span></span>

<span data-ttu-id="a73a0-111">Un sistema de administración de documentación actúa como un repositorio central para los documentos y ayuda a garantizar que solo esté disponible la última revisión de un documento.</span><span class="sxs-lookup"><span data-stu-id="a73a0-111">A documentation management system acts as a central repository for documents and helps ensure that only the latest revision of a document is available.</span></span> <span data-ttu-id="a73a0-112">También puede considerar la posibilidad de archivar la versión anterior del documento como referencia.</span><span class="sxs-lookup"><span data-stu-id="a73a0-112">You can also consider archiving the older version of the document for reference.</span></span> <span data-ttu-id="a73a0-113">Lync Server ofrece una funcionalidad adecuada para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="a73a0-113">Lync Server provides functionality suitable to this task.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a73a0-114">Databases</span><span class="sxs-lookup"><span data-stu-id="a73a0-114">Databases</span></span>

<span data-ttu-id="a73a0-115">Se trataron varias herramientas y funciones de administración que resultan adecuadas para usar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a73a0-115">Several tools and management functions were discussed that are suited to using databases.</span></span> <span data-ttu-id="a73a0-116">Es probable que el proceso de administración de la configuración use procesos automatizados que almacenen grandes cantidades de datos que requieran indización y búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a73a0-116">The configuration management process is likely to use automated processes that store large amounts of data that require indexing and searching.</span></span> <span data-ttu-id="a73a0-117">El personal de soporte técnico puede buscar en una base de datos de problemas y soluciones anteriores al solucionar problemas nuevos.</span><span class="sxs-lookup"><span data-stu-id="a73a0-117">Support staff may search a database of past issues and resolutions when troubleshooting new issues.</span></span>

<span data-ttu-id="a73a0-118">Es probable que se usen diferentes bases de datos para distintos fines.</span><span class="sxs-lookup"><span data-stu-id="a73a0-118">It is likely that there will be different databases being used for different purposes.</span></span> <span data-ttu-id="a73a0-119">Decida si estas bases de datos deben vincularse o combinarse.</span><span class="sxs-lookup"><span data-stu-id="a73a0-119">Decide if these databases should be linked or combined.</span></span> <span data-ttu-id="a73a0-120">Por ejemplo, si el servicio de asistencia al cliente identifica varios problemas con un tema común (como software nuevo que causa un problema con un adaptador de red determinado), el personal de soporte técnico puede consultar la base de datos de configuración para predecir cuántos equipos podrían verse afectados.</span><span class="sxs-lookup"><span data-stu-id="a73a0-120">For example, if the service desk identifies several issues with a common theme (such as new software causing an issue with a particular network adapter), the support staff can query the configuration database to predict how many computers might be affected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

