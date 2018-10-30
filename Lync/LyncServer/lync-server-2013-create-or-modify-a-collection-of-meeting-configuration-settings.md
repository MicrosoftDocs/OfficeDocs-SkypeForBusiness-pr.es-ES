---
title: "Crear/modificar conjunto de opciones de configuración reuniones en Lync Server 2013"
TOCTitle: "Créa. ou modif. d’une coll. de param. de conf. de réunion ds Lync Server 2013"
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49889691
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de un conjunto de opciones de configuración de reuniones en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

Use la configuración de la página Configuración de reunión para definir diversas características de la experiencia de participar en una reunión. Normalmente, la participación se rige por la configuración global. También puede crear configuraciones de participación en reuniones en el nivel de sitio y en el nivel de grupo de servidores. Si crea una configuración en el nivel de grupo de servidores, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración en el nivel de grupo de servidores, se aplicará la configuración del nivel de sitio, si existe. Si no define la configuración en el nivel de sitio, se aplicará la configuración global a todas las reuniones.

## Para crear nuevas configuraciones de participación en reuniones

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

4.  En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:
    
      - Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.
    
      - Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.

5.  Para redirigir a los participantes que realizaron la llamada desde una red telefónica conmutada (RTC) a través de la sala de espera, desactive la casilla **Los autores de llamadas RTC no pasan por la sala de espera**. Normalmente, los participantes que efectúen la llamada desde la RTC obtendrán acceso directamente a la reunión.

6.  Para configurar quién puede ser moderador en una reunión, en **Designar como moderador**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para que solo sea moderador el organizador, haga clic en **Ninguno**.
    
      - Para que solo sean moderadores los participantes que pertenezcan a la organización, haga clic en **Compañía**. Esta es la configuración que se aplica normalmente.
    
      - Para que cualquier participante sea moderador, haga clic en **Todos**.

7.  Para que el moderador pueda seleccionar un tipo de conferencia cuando se programe una reunión, desactive la casilla **Tipo de conferencia asignada de forma predeterminada**. Normalmente, el tipo de conferencia se asigna automáticamente.

8.  Para evitar que se admitan automáticamente a usuarios anónimos (sin autenticar), desactive la casilla **Admitir usuarios anónimos de forma predeterminada**. Normalmente, los usuarios anónimos se admiten automáticamente en las reuniones.

9.  Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente. Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB. Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión. Si no incluye una dirección URL de ayuda personalizada, en la invitación aparecerá la dirección URL de ayuda habitual para Lync.
    
      - Para personalizar el logotipo que aparece en la invitación de la reunión, en **Dirección URL del logotipo**, especifique la ubicación del logotipo.
        

        > [!NOTE]
        > El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles.

    
      - Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, especifique la ubicación del texto de ayuda.
    
      - Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, especifique la ubicación del logotipo.
    
      - Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.

10. Haga clic en **Confirmar**.

## Para modificar una colección de configuraciones de reunión existente

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.

4.  En la lista de configuraciones de la reunión, haga clic en la configuración que desee cambiar, luego, haga clic en **Editar** y, por último, en **Mostrar detalles**.

5.  En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.

6.  Haga clic en **Confirmar**.

## Crear configuraciones de reunión nuevas con cmdlets de Windows PowerShell

Las configuraciones de reunión también se pueden crear (si bien solo en el ámbito del sitio) con Windows PowerShell y el cmdlet New-CsMeetingConfiguration. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear configuraciones de reunión que usen los valores predeterminados

  - Este comando crea un conjunto de configuraciones de reunión nuevo para el sitio de Redmond:
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.

## Para cambiar un valor de propiedad al crear configuraciones de reunión

  - Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

## Para cambiar varios valores de propiedad al crear configuraciones de reunión

  - Puede cambiar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

Para más información, vea el tema de ayuda del cmdlet [New-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMeetingConfiguration).

