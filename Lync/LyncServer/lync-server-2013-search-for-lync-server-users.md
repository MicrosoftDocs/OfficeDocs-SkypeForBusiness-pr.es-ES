---
title: Búsqueda de usuarios de Lync Server
TOCTitle: Búsqueda de usuarios de Lync Server
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48275014
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Búsqueda de usuarios de Lync Server

 

_**Última modificación del tema:** 2014-05-14_

Puede usar los resultados de una consulta de búsqueda para configurar usuarios para Lync Server 2013. Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.

Puede buscar usuarios con Panel de control de Lync Server o el complemento Usuarios y equipos de Active Directory. En el siguiente procedimiento se describe cómo usar Panel de control de Lync Server para buscar usuarios.


> [!NOTE]
> En un entorno con tipología de bosque central, los resultados de una búsqueda a veces no son muy precisos cuando se busca a un usuario por su dirección de correo electrónico. En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet <STRONG>Get-CSUser</STRONG>.



## Para buscar uno o más usuarios

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios** .

4.  En el cuadro **Buscar usuarios** , escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar** .

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro** .
    
    2.  Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista **Igual a** , haga clic en **Igual a** o **No igual a** .
    
    4.  En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar** .

6.  Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda** . Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.

## Vea también

#### Otros recursos

[Ver información sobre las cuentas de usuario habilitadas para Lync Server 2013](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Habilitar y deshabilitar usuarios para Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

