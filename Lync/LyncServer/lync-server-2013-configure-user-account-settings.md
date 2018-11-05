---
title: 'Lync Server 2013: Configurar una cuenta de usuario'
TOCTitle: Configurar una cuenta de usuario
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48276439
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la cuenta de usuario en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Los usuarios de acceso telefónico escriben su número de teléfono o extensión y un PIN para participar en conferencias como usuarios autenticados. El **URI de línea** de telefonía especificado en las cuentas de usuario de Lync Server es obligatorio para la autenticación.

En el procedimiento de este tema se describe cómo asignar un **URI de línea** para una sola cuenta de usuario. Si desea asignar un **URI de línea** para varias cuentas de usuarios, puede crear un script que use el cmdlet **Set-CsUser**. Para más información sobre el uso de un script de ejemplo para asignar un **URI de línea** a varias cuentas de usuarios, consulte "Asignar URI de línea a varios usuarios" en [http://go.microsoft.com/fwlink/?linkid=196945\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=196945%26clcid=0xc0a).

## Para configurar las opciones de cuenta de usuario

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** .

4.  En el campo de búsqueda, escriba el nombre del usuario que desea configurar para las conferencias de acceso telefónico local o haga clic en **Agregar filtro** para especificar campos de búsqueda y, a continuación, haga clic en **Buscar** .

5.  Haga doble clic en el nombre de usuario para abrir el cuadro de diálogo **Editar usuario de Lync Server**.

6.  En **Telefonía** , en el campo **URI de línea** , escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).
    

    > [!NOTE]
    > Puede especificar un <STRONG>URI de línea</STRONG> solo si la <STRONG>Telefonía</STRONG> está establecida en <STRONG>Solo de PC a PC</STRONG> , <STRONG>Telefonía IP empresarial</STRONG> , <STRONG>Control remoto de llamadas</STRONG> o <STRONG>Control remoto de llamadas</STRONG> .



7.  Haga clic en **Confirmar** .

