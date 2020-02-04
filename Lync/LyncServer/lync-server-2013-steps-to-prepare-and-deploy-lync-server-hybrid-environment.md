---
title: 'Lync Server 2013: Pasos para preparar e implementar el entorno híbrido de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Pasos para preparar e implementar el entorno híbrido de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_

En la tabla siguiente se enumeran los pasos necesarios para preparar el entorno para una implementación híbrida con Skype empresarial online y Microsoft Office 365.


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
<td></td>
<td><p>Crear una cuenta de inquilino para Office 365 y habilitar Lync Online</p></td>
<td><p>Obtenga más información sobre Office 365 y Lync Online en <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Para asegurarse de que su entorno está listo para Office 365, consulte los <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisitos del sistema</a>.</p>
<p>Para obtener detalles sobre la configuración de Office 365, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Introducción a office 365</a> y <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">configurar Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Agregue su dominio y compruebe la propiedad</p></td>
<td><p>Su dominio se denomina también a veces <em>dominio personal</em>. Agregue su dominio a su inquilino de Office 365 y después siga los pasos para validar el dominio con Office 365. Esto se hace para confirmar que usted es el propietario del dominio.</p>
<p>Para agregar su dominio a su inquilino de Office 365, siga los pasos que se describen en <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Agregar su dominio a office 365</a>.</p>
<p>Complete todos los pasos de cada sección del tema, incluida &quot;la edición de registros DNS para los servicios de Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Comprobar la preparación del entorno</p></td>
<td><p>Puede usar el Asistente de configuración de Office 365 para ayudarle a implementar Office 365. Para obtener más información, vea <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">usar el Asistente de configuración para determinar la preparación de Office 365</a>.</p>
<p>Para obtener más información sobre cómo usar la herramienta e implementar Office 365, consulte la <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guía de implementación de office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Prepararse para la sincronización de Active Directory</p></td>
<td><p>La sincronización de Active Directory mantiene su Active Directory local sincronizado continuamente con Office 365. Esto le permite no solo crear versiones sincronizadas de cada grupo y cuenta de usuario, sino que también le permite la sincronización de la lista global de direcciones (GAL) desde su entorno de Microsoft Exchange Server local con Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Debe sincronizar las cuentas de AD de todos los usuarios de Lync de su organización entre las implementaciones de Lync locales y en línea, incluso si los usuarios no se mueven a Lync Online. Si no sincroniza todos los usuarios, puede ser que la comunicación entre los usuarios locales y en línea de su organización no funcione como se podría esperar.


</div>
<p>Para preparar el entorno para la sincronización de Active Directory, siga los pasos que se describen en <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Guía básica de sincronización de directorios</a>, incluida la configuración del inicio de sesión único.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Crear certificados para servicios de Federación de Active Directory (AD FS)</p></td>
<td><p>Tendrá que crear los certificados que se usan para la Federación de identidades con Office 365. Para obtener más información, consulte la sección "certificados de servidor de Federación" de los temas planear e implementar AD FS para su uso con el inicio de sesión único en la <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">lista de comprobación: Use AD FS para implementar y administrar el inicio de sesión único</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Asignar certificados para AD FS</p></td>
<td><p>Después de crear los certificados que se usan para la Federación de identidades con Office 365, debe instalarlos y asignarlos.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Mover los usuarios piloto a Skype empresarial online</p></td>
<td><p>Una vez completados los pasos para preparar y configurar su entorno para Skype empresarial online, puede empezar a mover los usuarios piloto a Lync Online.</p>
<p>Consulte <a href="lync-server-2013-move-users-to-lync-online.md">mover usuarios a Lync Online en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Administrar usuarios en una implementación híbrida</p></td>
<td><p>Para obtener detalles sobre cómo administrar usuarios en una implementación híbrida, consulte <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrar usuarios en una implementación híbrida de Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

