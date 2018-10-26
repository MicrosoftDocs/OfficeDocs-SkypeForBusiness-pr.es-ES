---
title: "Lync Server 2013: Pasos para preparar e implementar el entorno híbrido de Lync Server"
TOCTitle: Pasos para preparar e implementar el entorno híbrido de Lync Server 2013
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48276190
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Pasos para preparar e implementar el entorno híbrido de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

En la tabla siguiente se incluyen los pasos necesarios para preparar el entorno para una implementación híbrida con Microsoft Lync Online y Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>¿Completado?</th>
<th>Paso</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p>Cree una cuenta de inquilino para Office 365 y habilite Lync Online</p></td>
<td><p>Obtenga información sobre Office 365 y Lync Online en <a href="http://go.microsoft.com/fwlink/?linkid=254980">Office 365</a>.</p>
<p>Para asegurarse de que su entorno está preparado para Office 365, vea los <a href="http://go.microsoft.com/fwlink/p/?linkid=401408">Requisitos del sistema</a>.</p>
<p>Para más información sobre la configuración de Office 365, vea <a href="http://go.microsoft.com/fwlink/?linkid=254982">Introducción a Office 365</a> y <a href="http://go.microsoft.com/fwlink/?linkid=254979">Configurar Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Agregue su dominio y compruebe la propiedad</p></td>
<td><p>Su dominio se denomina también a veces <em>dominio personal</em> . Agregue su dominio a su inquilino de Office 365 (en Edog) y después siga los pasos para validar el dominio con Office 365. Esto se hace para confirmar que usted es el propietario del dominio.</p>
<p>Para agregar su dominio a su inquilino de Office 365, siga los pasos descritos en <a href="http://go.microsoft.com/fwlink/?linkid=254983">Agregar un dominio a Office 365</a>.</p>
<p>Complete todos los pasos de cada sección del tema, incluido “Editar registros DNS para los servicios de Office 365”.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Verifique la preparación del entorno</p></td>
<td><p>Puede el Asistente para la instalación de Office 365 para implementar Office 365. Para obtener más información, vea <a href="http://go.microsoft.com/fwlink/p/?linkid=254985">Usar el Asistente para la instalación para determinar si Office 365 está listo</a></p>
<p>Para obtener información sobre cómo usar la herramienta e implementar Office 365, vea la <a href="http://go.microsoft.com/fwlink/p/?linkid=257337">guía de implementación de Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Preparación para la sincronización de Active Directory</p></td>
<td><p>La sincronización de Active Directory mantiene su Active Directory local continuamente sincronizado con Office 365. Esto le permite no solo crear versiones sincronizadas de cada grupo y cuenta de usuario, sino que también le permite la sincronización de la lista global de direcciones (GAL) desde su entorno de Microsoft Exchange Server local con Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Debe sincronizar las cuentas para todos los usuarios de Lync de su organización entre sus implementaciones de Lync local y en línea, incluso si los usuarios no se mueven a Lync Online. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.


</div>
<p>Para preparar su entorno para la sincronización de Active Directory, siga los pasos descritos en <a href="http://go.microsoft.com/fwlink/p/?linkid=254988">Sincronización de directorios: Guía básica</a>, que incluye la configuración del inicio de sesión único.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Creación de certificados para Servicios de federación de Active Directory (AD FS)</p></td>
<td><p>Tendrá que crear los certificados que se usarán para la federación de identidades con Office 365. Para obtener más información, vea la sección “Certificados de servidor de federación” del tema Planear e implementar AD FS para su uso con el inicio de sesión único, en <a href="http://go.microsoft.com/fwlink/p/?linkid=285376">Lista de comprobación: Usar AD FS para implementar y administrar el inicio de sesión único</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Asignar certificados para AD FS</p></td>
<td><p>Una vez que cree los certificados que se usan para la federación de identidades con Office 365, tendrá que instalarlos y asignarlos.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Mover los usuarios piloto a Skype Empresarial Online</p></td>
<td><p>Una vez haya completado los pasos para preparar y configurar el entorno para Skype Empresarial Online, puede empezar a mover los usuarios piloto a Lync Online.</p>
<p>Vea <a href="lync-server-2013-move-users-to-lync-online.md">Mover usuarios a Lync Online en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Administrar usuarios en una implementación híbrida</p></td>
<td><p>Para más información sobre cómo administrar usuarios en una implementación híbrida, vea <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administrar usuarios en una implementación híbrida de Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

