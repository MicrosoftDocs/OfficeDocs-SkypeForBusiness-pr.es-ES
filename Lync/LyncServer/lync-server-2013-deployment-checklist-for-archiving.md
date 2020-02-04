---
title: 'Lync Server 2013: Lista de comprobación para la implementación del archivado'
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
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lista de comprobación para la implementación del archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

El archivado se instala automáticamente en cada servidor front-end de su implementación de Lync Server 2013, pero debe configurarlo antes de poder usarlo. Los pasos necesarios para configurarlo, como se resume en esta sección, constituyen la implementación del archivado.

<div>

## <a name="deployment-sequence"></a>Secuencia de implementación

La forma en que configure el archivado dependerá de la opción de almacenamiento que elija:

  - Si usa la integración de Microsoft Exchange para todos los usuarios de su implementación, no necesita configurar las directivas de archivado de Lync Server 2013 para sus usuarios. En su lugar, configure las directivas de retención local de Exchange para admitir el archivado de usuarios alojados en Exchange 2013, con sus buzones en conservación local. Para obtener más información sobre cómo configurar estas directivas, consulte la documentación del producto Exchange 2013.

  - Si no usa la integración de Microsoft Exchange para todos los usuarios de su implementación, debe agregar bases de datos de archivado de Lync Server (bases de datos de SQL Server) a su topología y luego publicarla, así como configurar las directivas y la configuración de los usuarios, antes de poder Archive datos para esos usuarios. Puede implementar bases de datos de archivado al mismo tiempo que implementa su Topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar las bases de datos de archivado agregándolas a una implementación existente.

Si habilita el archivado en un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos front-end y servidores Standard Edition de su implementación. Esto se debe a que los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación grupal grupal o a reuniones hospedadas en un grupo diferente. Si el archivo no está habilitado en el grupo en el que está hospedada la conversación o la reunión, es posible que la sesión completa no se Archive. En estos casos, los mensajes instantáneos con usuarios habilitados para archivado aún pueden archivarse, pero no para archivos de contenido de conferencias, y para eventos de unión o salida de conferencia.

<div>


> [!IMPORTANT]  
> Si el archivado es importante en su organización por razones de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel correspondiente y habilitarlo para todos los usuarios apropiados, antes de habilitar esos usuarios para Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Proceso de implementación de archivado

La tabla siguiente proporciona información general de los pasos necesarios para implementar el archivado en una topología existente.


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
<th>Roles y pertenencias a grupos</th>
<th>Documentación</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar los requisitos previos de hardware y software</strong></p></td>
<td><ul>
<li><p>Para usar la integración de Microsoft Exchange (con Exchange 2013 para archivar el almacenamiento para algunos o todos los usuarios), necesita una implementación de Exchange 2013 existente.</p></li>
<li><p>Para usar bases de datos de archivado independientes (con bases de datos de SQL Server) para archivar el almacenamiento de algunos o todos los usuarios, SQL Server en el servidor que almacenará los datos de archivado.</p></li>
</ul>
<div>

> [!NOTE]  
> El archivado se ejecuta en servidores front-end de un grupo de servidores Enterprise y servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.


</div></td>
<td><p>Usuario de dominio que es miembro del grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación de soporte técnico.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Compatibilidad con el software de servidor y la infraestructura en Lync Server 2013</a> en la documentación de soporte técnico.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivar en Lync Server 2013</a> en la documentación de planeación.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestructura para archivar en Lync Server 2013</a> en la documentación de implementación.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Compatibilidad de integración de Exchange Server y SharePoint en Lync server 2013</a> en la documentación de soporte técnico.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para admitir el archivado (solo si no se usa la integración de Microsoft Exchange para todos los usuarios de la implementación)</strong></p></td>
<td><p>Ejecute el generador de topología para agregar bases de datos de archivo de Lync Server 2013 (bases de datos de SQL Server) a la topología y, después, publique la topología.</p></td>
<td><p>Para definir una topología para incorporar bases de datos de archivado, una cuenta que sea miembro del grupo usuarios locales.</p>
<p>Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para el almacén de archivos de Lync Server 2013 (para que topología pueda configurar las DACL obligatorias).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Agregar bases de datos de archivado a una implementación existente de Lync Server 2013</a> en la documentación de implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar la autenticación de servidor a servidor (solo si se usa la integración de Microsoft Exchange)</strong></p></td>
<td><p>Configure servidores para habilitar la autenticación entre Lync Server 2013 y Exchange 2013. Le recomendamos que ejecute <strong>Test-CsExchangeStorageConnectivity testuser_sipUri: contenedor de carpetas</strong> para validar la Conectividad del almacenamiento de archivado de Exchange antes de habilitar el archivado.</p></td>
<td><p>Una cuenta con los permisos necesarios para administrar certificados en los servidores.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socios en Lync server 2013</a> en la documentación de implementación o en la documentación de operaciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurar directivas y configuraciones de archivado</strong></p></td>
<td><p>Configurar el archivado, incluyendo si se debe usar la integración de Microsoft Exchange, la directiva global y las directivas de sitio y de usuario (si no se usa la integración de Microsoft Exchange para todo el almacenamiento de datos) y opciones de archivado específicas, como los datos y el modo crítico exportar y purgar.</p>
<p>Si usa la integración de Microsoft Exchange, configure las directivas de retención local de Exchange según corresponda.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne los usuarios al rol CSArchivingAdministrator o CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configurar la compatibilidad para archivar en Lync Server 2013</a> en la documentación de implementación.</p>
<p>Documentación de producto de Exchange (si se usa la integración de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Implementar Lync Server y Microsoft Exchange en bosques diferentes

Si Microsoft Exchange Server no está implementado en el mismo bosque que Lync Server, debe asegurarse de que los siguientes atributos de Exchange Active Directory estén sincronizados con el bosque donde se ha implementado Lync Server:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Este es un atributo de varios valores. Al sincronizarlo, los valores se necesitan combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

