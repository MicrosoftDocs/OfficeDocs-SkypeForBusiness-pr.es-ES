---
title: 'Lync Server 2013: Lista de comprobación para la implementación del archivado'
TOCTitle: Lista de comprobación para la implementación del archivado
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48275695
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lista de comprobación para la implementación del archivado en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Aunque el archivo se instala automáticamente en cada uno de los servidores front-end de su implementación de Lync Server 2013, necesitará configurarlo antes de usarlo. Los pasos necesarios para hacerlo, que se resumen en esta sección, constituyen la implementación del archivado.

## Secuencia de implementación

La configuración del archivo depende de la opción de almacenamiento que se elija:

  - Si utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, no será necesario que configure las directivas de archivado de Lync Server 2013 para sus usuarios. Configure, en cambio, las directivas de la característica In-Place Hold de Exchange para permitir el archivado a los usuarios hospedados en Exchange 2013, quienes tienen sus buzones de correo almacenados en In-Place Hold. Para más detalles sobre la configuración de estas directas, consulte la documentación del producto Exchange 2013.

  - Si no utiliza la integración de Microsoft Exchange para todos los usuarios de la implementación, agregue las bases de datos de archivado de Lync Server (bases de datos de SQL Server) a la topología. Después, publique la topología y configure las directivas y los ajustes relativos a los usuarios para poder archivar datos para los mismos. Puede implementar bases de datos de archivado a la vez que implementa su topología inicial o después de implementar, como mínimo, un grupo de servidores front-end o un servidor Standard Edition. En este documento se describe cómo implementar bases de datos de archivado agregándolas a una implementación existente.

Si habilita el archivado en un grupo de servidores front-end o un servidor Standard Edition, será necesario que lo habilite para todos los demás grupos de servidores de front-end y los servidores Standard Edition de su implementación. Esto se debe a que los usuarios cuyas comunicaciones se deben archivar pueden ser invitados a una conversación de mensajería instantánea en grupo o a reuniones hospedadas en un grupo de servidores diferente. Si el archivado no está habilitado en el grupo de servidores donde se hospeda la conversación o la reunión, puede que no se almacene toda la sesión. En estos casos, se podrán seguir archivando los mensajes instantáneos de los usuarios que tengan habilitado el archivado, pero no los archivos de contenido de conferencia ni los eventos creados al unirse a conferencias o abandonarlas.

> [!IMPORTANT]  
> Si el archivado es esencial para su organización por motivos de cumplimiento, asegúrese de implementarlo, configurar directivas y otras opciones en el nivel adecuado y habilitarlo para los usuarios que corresponda antes de habilitar a estos usuarios para Lync Server 2013.



## Proceso de implementación de archivado

La tabla siguiente proporciona una visión general de los pasos necesarios para implementar el archivado en una topología existente.


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
<li><p>Para utilizar la implementación de Microsoft Exchange (con Exchange 2013 para el almacén de archivado para algunos o todos los usuarios), necesitará una implementación de Exchange 2013 existente.</p></li>
<li><p>Para usar bases de datos independientes (con bases de datos de SQL Server) para el almacén de archivado para algunos o todos los usuarios, necesitará SQL Server en el servidor que almacenará los datos de archivado.</p></li>
</ul>
<div>

> [!NOTE]
> El archivado se ejecuta en servidores front-end de un grupo de servidores Enterprise y en servidores Standard Edition. No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.


</div></td>
<td><p>Usuario de dominio que es miembro del grupo de administradores locales.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware admitido en Lync Server 2013</a> en la documentación de compatibilidad.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación de compatibilidad.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para archivado en Lync Server 2013</a> en la documentación de planeación</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestructura de archivado en Lync Server 2013</a> en la documentación de implementación.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Compatibilidad de la integración Exchange Server y SharePoint en Lync Server 2013</a> en la documentación de compatibilidad.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crear la topología interna adecuada para permitir el archivado (solo si no se están usando la integración de Microsoft Exchange para todos los usuarios de la implementación)</strong></p></td>
<td><p>Ejecute Generador de topologías para agregar las bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) a la topología y, después, publique la topología.</p></td>
<td><p>Para definir una topología para incorporar bases de datos de archivado, se necesita una cuenta que pertenezca al grupo de usuarios locales.</p>
<p>Para publicar la topología, una cuenta que es miembro del grupo de administradores de domino y del grupo RTCUniversalServerAdmins, que tiene permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos que se usará para el almacén de archivos de Lync Server 2013 (de modo que el Generador de topologías pueda configurar las DACL necesarias).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adición de bases de datos de archivado a una implementación existente de Lync Server 2013</a> en la documentación de implementación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar la autenticación de servidor a servidor (solo si se está usando la integración de Microsoft Exchange)</strong></p></td>
<td><p>Configure los servidores para habilitar la autenticación entre Lync Server 2013 y Exchange 2013. Recomendamos ejecutar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> para validar la conectividad del almacén de archivado de Exchange antes de habilitar el archivado.</p></td>
<td><p>Una cuenta con los permisos necesarios para administrar certificados en los servidores.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013</a> en la documentación sobre implementación u operaciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurar configuraciones y directivas de archivado</strong></p></td>
<td><p>Para configurar el archivado, especifique si desea usar la integración de Microsoft Exchange y configure la directiva global, las directivas de usuario y de sitio que haya (cuando no se use la integración de Microsoft Exchange para el almacenamiento de los datos) y las opciones específicas de archivado, como el modo crítico y la exportación y depuración de datos.</p>
<p>Si está usando la integración de Microsoft Exchange, configure las directivas de la característica In-Place Hold de Exchange según corresponda.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asigne los usuarios al rol CSArchivingAdministrator o CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configurar compatibilidad con archivado en Lync Server 2013</a> en la documentación de implementación.</p>
<p>Documentación del producto Exchange (si se está usando la integración de Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


## Implementación de Lync Server y de Microsoft Exchange en bosques diferentes

Si Microsoft Exchange Server no se implementó en el mismo bosque que Lync Server, asegúrese de que los atributos de Active Directory de Exchange siguientes están sincronizados con el bosque en el que Lync Server está implementado:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Este es un atributo de varios valores. Al sincronizar el atributo, los valores se deben combinar, no reemplazar, para garantizar que no se pierdan los valores existentes.

