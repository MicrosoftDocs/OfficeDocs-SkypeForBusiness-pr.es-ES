---
title: 'Lync Server 2013: lista de comprobación para la implementación del archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccec3917e892d1ba6c3e1841773c77e8c2d015d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514533"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lista de comprobación para la implementación del archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

El archivado se instala automáticamente en cada uno de los servidores front-end de la implementación de Lync Server 2013, pero es necesario configurarlo antes de poder usarlo. Los pasos necesarios para configurarlo, como se resume en esta sección, constituyen la implementación del archivado.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

La configuración del archivado depende de la opción de almacenamiento que elija:

  - Si usa la integración de Microsoft Exchange para todos los usuarios de la implementación, no es necesario que configure las directivas de archivado de Lync Server 2013 para los usuarios. En su lugar, configure las directivas de suspensión de In-Place de Exchange para admitir el archivado para los usuarios hospedados en Exchange 2013, con sus buzones colocados en In-Place retenido. Para obtener más información acerca de la configuración de estas directivas, consulte la documentación del producto de Exchange 2013.

  - Si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación, debe agregar bases de datos de archivado de Lync Server (bases de datos de SQL Server) a la topología y, a continuación, publicarla, así como configurar directivas y opciones de configuración para los usuarios, antes de poder archivar datos para esos usuarios. Puede implementar las bases de datos de archivado al mismo tiempo que implementa la topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar las bases de datos de archivado agregándolas a una implementación existente.

Si habilita el archivado en un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos de servidores front-end y servidores Standard Edition de la implementación. Esto se debe a que los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación de mensajería instantánea en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo en el que está hospedada la conversación o la reunión, es posible que no se Archive la sesión completa. En estos casos, los mensajes instantáneos con usuarios habilitados para archivado todavía pueden archivarse, pero no para los archivos de contenido de conferencias, ni eventos de unión o abandono de conferencias.

<div>


> [!IMPORTANT]  
> Si el archivado es crítico en su organización por motivos de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel adecuado y habilitarlo para todos los usuarios apropiados, antes de habilitar a esos usuarios para Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Proceso de implementación de archivado

En la tabla siguiente se proporciona información general sobre los pasos necesarios para implementar el archivado en una topología existente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Pasos</th>
<th>Roles y pertenencia a grupos</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instale el hardware y el software necesario como requisito previo</strong></p></td>
<td><ul>
<li><p>Para usar la integración de Microsoft Exchange (con Exchange 2013 para el almacenamiento de archivado para algunos o todos los usuarios), necesitará una implementación de Exchange 2013 existente.</p></li>
<li><p>Para usar bases de datos de archivado independientes (con bases de datos de SQL Server) para el almacenamiento de archivado para algunos o todos los usuarios, SQL Server en el servidor en el que se almacenarán los datos de archivado.</p></li>
</ul>
<div>

> [!NOTE]  
> El archivado se ejecuta en los servidores front-end de un grupo de servidores Enterprise y servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.


</div></td>
<td><p>Usuario de dominio que es miembro del grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación sobre compatibilidad.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para el archivado en Lync Server 2013</a> en la documentación referente a la planeación.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar los sistemas y la infraestructura para el archivado en Lync Server 2013</a> en la documentación sobre implementación.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Compatibilidad con la integración de Exchange Server y SharePoint en Lync server 2013</a> en la documentación sobre compatibilidad.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir el archivado (solo si no se usa la integración de Microsoft Exchange para todos los usuarios de la implementación)</strong></p></td>
<td><p>Ejecute el generador de topologías para agregar bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) a la topología y, a continuación, publique la topología.</p></td>
<td><p>Para definir una topología para incorporar bases de datos de archivado, una cuenta que sea miembro del grupo de usuarios locales.</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para su uso en el almacén de archivos de Lync Server 2013 (para que el generador de topologías pueda configurar las DACL necesarias).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adición de bases de datos de archivado a una implementación existente de Lync Server 2013</a> en la documentación de implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar la autenticación de servidor a servidor (solo si se usa la integración de Microsoft Exchange)</strong></p></td>
<td><p>Configure los servidores para habilitar la autenticación entre Lync Server 2013 y Exchange 2013. Se recomienda ejecutar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri: contenedor de carpetas</strong> para validar la Conectividad del almacenamiento de archivado de Exchange antes de habilitar el archivado.</p></td>
<td><p>Una cuenta con los permisos adecuados para administrar certificados en los servidores.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013</a> en la documentación de implementación o en la documentación de operaciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configuración de directivas y configuraciones de archivado</strong></p></td>
<td><p>Configurar el archivado, incluido si se va a usar la integración de Microsoft Exchange, la directiva global y las directivas de sitio y de usuario (cuando no se usa la integración de Microsoft Exchange para todo el almacenamiento de datos) y opciones de archivado específicas, como el modo crítico y la exportación y depuración de datos.</p>
<p>Si usa la integración de Microsoft Exchange, configure las directivas de retención de Exchange In-Place según corresponda.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asignar usuarios al rol rol csarchivingadministrator o CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring Support for archiving in Lync Server 2013</a> en la documentación de implementación.</p>
<p>Documentación del producto de Exchange (si se usa la integración de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Implementación de Lync Server y Microsoft Exchange en bosques diferentes

Si Microsoft Exchange Server no se implementa en el mismo bosque que Lync Server, debe asegurarse de que los siguientes atributos de Active Directory de Exchange están sincronizados con el bosque en el que se ha implementado Lync Server:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Se trata de un atributo de varios valores. Al sincronizar este atributo, debe combinar los valores, no reemplazarlos para asegurarse de que no se pierdan los valores existentes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

