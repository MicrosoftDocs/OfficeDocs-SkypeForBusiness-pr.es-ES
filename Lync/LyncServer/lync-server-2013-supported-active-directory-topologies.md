---
title: 'Lync Server 2013: topologías admitidas de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9437df126889aefb8400b50d118d44dac12f285d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologías de Active Directory admitidas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-02_

Lync Server 2013 admite las mismas topologías de servicios de dominio de Active Directory que Microsoft Lync Server 2010 y Microsoft Office Communications Server 2007 R2. Se admiten las siguientes topologías:

  - Un solo bosque con un solo dominio

  - Un solo bosque con un solo árbol y varios dominios

  - Un solo bosque con varios árboles y espacios de nombres separados

  - Varios bosques en una topología de bosque central

  - Varios bosques en una topología de bosque de recursos

  - Varios bosques en una topología de bosque de recursos de Lync con Exchange Online

En la siguiente figura se identifican los iconos utilizados en las ilustraciones de esta sección.

**Leyenda de las ilustraciones de topología**

![Leyenda de las ilustraciones de topología](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Leyenda de las ilustraciones de topología")

<div>

## <a name="single-forest-single-domain"></a>Un solo bosque, un solo dominio

La topología de Active Directory más sencilla compatible con Lync Server, un bosque de dominio único, es una topología común.

En la siguiente figura se muestra una implementación de Lync Server en una topología de Active Directory de un solo dominio.

**Topología de dominio único**

![Topología de dominio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topología de dominio único")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Un solo bosque, varios dominios

Otra topología de Active Directory compatible con Lync Server es un único bosque que consta de un dominio raíz y uno o más dominios secundarios. En este tipo de topología de Active Directory, el dominio donde se crean los usuarios puede ser diferente del dominio en el que se va a implementar Lync Server. Sin embargo, si implementa un grupo de servidores front-end, deberá implementar todos los servidores front-end del grupo en un dominio único. Lync Server Support for Windows universal Administrator Groups permite la administración entre dominios.

En la siguiente figura se muestra una implementación en un solo bosque con varios dominios. En esta figura, un icono de usuario muestra el dominio en el que está hospedada la cuenta de usuario y la flecha apunta al dominio donde reside el grupo de servidores de Lync Server. Entre las cuentas de usuario se incluyen las siguientes:

  - Cuentas de usuario dentro del mismo dominio que el grupo de Lync Server

  - Cuentas de usuario en un dominio diferente del grupo de servidores de Lync Server

  - Cuentas de usuario en un dominio secundario del dominio con el grupo de servidores de Lync Server

**Un solo bosque con varios dominios**

![Un solo bosque con varios dominios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Un solo bosque con varios dominios")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Un solo bosque, varios árboles

La topología de un solo bosque y varios árboles se compone de dos o más dominios que definen estructuras de árbol independientes y espacios de nombres de Active Directory independientes.

En la figura siguiente se muestra un solo bosque con varios árboles. En esta figura, un icono de usuario muestra el dominio en el que se hospeda la cuenta de usuario, una línea sólida a un grupo de Lync Server que reside en el mismo dominio o en otro diferente, y una línea discontinua apunta a un grupo de Lync Server que reside en un árbol diferente. Entre las cuentas de usuario se incluyen las siguientes:

  - Cuentas de usuario dentro del mismo dominio que el grupo de Lync Server

  - Cuentas de usuario en un dominio diferente de (pero el mismo árbol que) el grupo de Lync Server

  - Cuentas de usuario en un árbol diferente del grupo de Lync Server

**Un solo bosque con varios árboles**

![Un solo bosque con varios árboles](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Un solo bosque con varios árboles")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Varios bosques, bosque central

Lync Server admite varios bosques que están configurados en una topología de bosque central. Las topologías de bosque central utilizan objetos de contacto en el bosque central para representar a los usuarios en los otros bosques. El bosque central también hospeda las cuentas de usuario de cualquier usuario de este bosque. Un producto de sincronización de directorios, como, por ejemplo, Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario en la organización: cuando se crea una nueva cuenta de usuario en uno de los bosques o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza el contacto correspondiente en el bosque central.

Un bosque central tiene las ventajas siguientes:

  - Los servidores que ejecutan Lync Server están centralizados dentro de un solo bosque.

  - Los usuarios pueden buscar otros usuarios y comunicarse con ellos en cualquier bosque.

  - Los usuarios pueden ver la presencia de otros usuarios en cualquier bosque.

  - El producto de sincronización de directorios automatiza la adición y la eliminación de los objetos de contacto en el bosque central cuando se crean y se quitan cuentas de usuario.

En la siguiente figura se muestra una topología de bosque central. En esta figura, hay relaciones de confianza bidireccionales entre el dominio que hospeda Lync Server, que se encuentra en el bosque central, y cada dominio solo de usuario, que se encuentra en un bosque independiente. No es necesario extender el esquema de los bosques de usuarios independientes.

**Topología de bosque central**

![Topología de bosque central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topología de bosque central")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Varios bosques, bosque de recursos

En una topología de bosque de recursos, un bosque está dedicado a ejecutar aplicaciones de servidor, como Microsoft Exchange Server y Lync Server. El bosque de recursos hospeda las aplicaciones de servidor y una representación sincronizada del objeto de usuario activo, pero no contiene cuentas de usuario habilitadas para inicio de sesión. El bosque de recursos actúa como un entorno de servicios compartidos para los otros bosques donde residen los objetos de usuario. Los bosques de usuarios tienen una relación de confianza de nivel de bosque con el bosque de recursos. Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios. Si Microsoft Exchange ya está implementado en el bosque de recursos, es posible que ya existan cuentas de usuario deshabilitadas. Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario. Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos.

Esta topología se puede usar para proporcionar una infraestructura compartida para servicios en organizaciones que administran varios bosques o para separar la administración de objetos de Active Directory de otra administración. Las empresas que necesitan aislar la administración de Active Directory por motivos de seguridad suelen elegir esta topología.

Esta topología ofrece la ventaja de limitar la necesidad de extender el esquema de Active Directory a un único bosque (es decir, el bosque de recursos).

El siguiente diagrama ilustra una topología de bosque de recursos.

**Topología de bosque de recursos**

![Topología de bosque de recursos de Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topología de bosque de recursos de Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Varios bosques en una topología de bosque de recursos de Lync con Exchange Online

En esta topología, uno o más bosques se encuentran en local y se dedican a hospedar cuentas de usuario de Active Directory. El bosque de recursos se encuentra fuera de la organización y lo mantiene un proveedor de hospedaje de terceros. El bosque de recursos contiene solo la implementación de Lync Server y una replicación sincronizada de las cuentas de usuario desde el bosque o las cuentas de usuario locales. No contiene cuentas de usuario habilitadas para inicio de sesión. Exchange se implementa en los bosques de cuentas de usuario locales integrados junto con Exchange Online (híbrido), o los servicios de correo electrónico para las cuentas de usuario locales se proporcionan exclusivamente por parte de Exchange Online.

El bosque de recursos actúa como un entorno de servicios compartidos para el bosque o los bosques de Active Directory locales donde residen los objetos de usuario. Los bosques de cuentas de usuario tienen una relación de confianza de nivel de bosque unidireccional con el bosque de recursos. Al implementar Lync Server en este tipo de topología, se crea un objeto de usuario deshabilitado en el bosque de recursos para cada cuenta de usuario en los bosques de usuarios. Un producto de sincronización de directorios, como MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), administra el ciclo de vida de las cuentas de usuario. Cuando se crea una nueva cuenta de usuario en uno de los bosques de usuarios o se elimina una cuenta de usuario de un bosque, el producto de sincronización de directorios sincroniza la representación de usuario correspondiente en el bosque de recursos. Para obtener más información acerca de la configuración de una implementación de varios bosques, vea [Deploying Lync in a multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

