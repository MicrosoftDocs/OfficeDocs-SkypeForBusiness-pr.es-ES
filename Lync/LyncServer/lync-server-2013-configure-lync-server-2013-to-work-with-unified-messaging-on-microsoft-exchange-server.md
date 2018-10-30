---
title: "Configurar Lync Server 2013 para la mensajería unificada en MS Exchange Server"
TOCTitle: Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48274461
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server

 

_**Última modificación del tema:** 2016-12-08_

Para realizar este paso hace falta la utilidad de integración de Mensajería unificada de Exchange (OcsUmUtil.exe). Esta herramienta se encuentra en el servidor Lync Server 2013 en la carpeta ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support.

## Ejecución de la utilidad de integración de MU de Exchange

La utilidad de integración de Mensajería unificada de Exchange se debe ejecutar desde una cuenta de usuario con las siguientes características:

  - Pertenencia a los grupos RTCUniversalServerAdmins y RtcUniversalUserAdmins (que incluyen permisos para leer la configuración de Mensajería unificada de Exchange Server).

  - Derechos de usuario dentro del dominio para crear objetos de contacto en el contenedor especificado de la unidad organizativa.

Al ejecutar la utilidad de integración de Mensajería unificada de Exchange, se realizan las tareas siguientes:

  - Se crean objetos de contacto para cada número de operador automático y acceso de suscriptor que vayan a usar los usuarios de Telefonía IP empresarial.

  - Se comprueba que el nombre de cada uno de los planes de marcado de Telefonía IP empresarial coincide con su contexto telefónico de plan de marcado de mensajería unificada (MU) correspondiente. Esta coincidencia es necesaria únicamente si el plan de marcado de la mensajería unificada se ejecuta en una versión de Exchange *anterior* a Exchange 2010 Service Pack 1 (SP1).

> [!IMPORTANT]  
> Antes de ejecutar la utilidad de integración de Mensajería unificada de Exchange, asegúrese de que ha llevado a cabo lo siguiente:
> <ul>
> <li><p>Crear uno o varios planes de marcado de Mensajería unificada de Exchange, tal y como se describe en la documentación de producto de Exchange.</p>
> <p>Para Microsoft Exchange Server 2010, consulte &quot;Crear un plan de marcado de mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=186177%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=186177&amp;clcid=0xC0A</a>.</p>
> <p>Para Microsoft Exchange Server 2007 Service Pack 1 (SP1), consulte &quot;Cómo crear un plan de marcado del URI del SIP de mensajería unificada&quot; en <a href="http://go.microsoft.com/fwlink/?linkid=185771%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=185771&amp;clcid=0xC0A</a>.</p></li>
> <li><p>Crear uno o varios planes de marcado de Lync Server correspondientes, tal y como se describe en <a href="lync-server-2013-create-a-dial-plan.md">Crear un plan de marcado en Lync Server 2013</a>.</p></li>
> <ul><li>Si está usando una versión de Exchange anterior a Microsoft Exchange Server 2010 SP1, deberá escribir el nombre de dominio completo (FQDN) del plan de marcado SIP de Mensajería unificada de Exchange (UM) correspondiente en el plan de marcado Lync Server 2013, en el campo <strong>Nombre sencillo</strong>. Si está usando Microsoft Exchange Server 2010 SP1 o el service pack más reciente, no es necesario que coincida el nombre del plan de marcado.</li></ul>
> <li>Crear un operador automático y asegurarse de que tanto el número de acceso del suscriptor y el número del operador automático están en formato E.164.</li></ul>


## Para ejecutar la utilidad de integración de MU de Exchange

1.  En un Servidor front-end, abra una ventana de símbolo del sistema y escriba **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support** . A continuación, pulse Entrar.

2.  Escriba **OcsUmUtil.exe** y pulse Entrar.

3.  Haga clic en **Cargar datos** para buscar todos los bosques de Exchange de confianza.

4.  En la lista **Planes de marcado de SIP**, seleccione un plan de marcado de SIP de MU para el que desee crear objetos de contacto y, a continuación, haga clic en **Agregar**.

5.  En el cuadro **Contacto**, acepte la unidad organizativa predeterminada o haga clic en **Examinar** para iniciar el **Selector de unidad organizativa**. En el cuadro **Selector de unidad organizativa**, puede seleccionar una unidad organizativa y hacer clic en **Aceptar**, o puede hacer clic en **Crear nueva unidad organizativa** para crear una nueva unidad organizativa en la raíz o en cualquier otra unidad organizativa del dominio (por ejemplo, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com") y, a continuación, hacer clic en **Aceptar**.
    

    > [!NOTE]
    > El nombre distintivo (DN) de la unidad organizativa que ha seleccionado o creado se muestra ahora en el cuadro <STRONG>Unidad organizativa</STRONG>.



6.  En el cuadro **Nombre**, acepte el nombre del plan de marcado predeterminado o escriba un nuevo nombre para mostrar para el objeto de contacto que está creando.
    

    > [!NOTE]
    > Por ejemplo, si va a crear un objeto de contacto de acceso de suscriptor, podría denominarlo simplemente Acceso de suscriptor.



7.  En el cuadro **Dirección SIP**, acepte la dirección SIP predeterminada o escriba una nueva dirección SIP.
    

    > [!NOTE]
    > Si escribe una nueva dirección SIP, esta debe empezar por <STRONG>SIP:</STRONG> (es decir, "SIP:" incluidos los dos puntos).



8.  En la lista **Servidor o grupo de servidores**, seleccione el servidor Standard Edition o el Grupo de servidores front-end en el que se va a habilitar el objeto de contacto.
    

    > [!NOTE]
    > Preferiblemente, el grupo de servidores que seleccione debe ser el mismo que el servidor en el que se han implementado los usuarios habilitados para Telefonía IP empresarial y MU de Exchange.



9.  En la lista **Número de teléfono**, seleccione **Escriba el número de teléfono** o **Use este número piloto de mensajería unificada de Exchange** y escriba un número de teléfono.

10. En la lista **Tipo de contacto**, seleccione el tipo de contacto que desea crear y, a continuación, haga clic en **Aceptar**.

11. Repita los pasos del 1 al 10 para los objetos de contacto adicionales que desee crear.
    

    > [!NOTE]
    > Debe crear al menos un contacto para cada operador automático. Si desea tener acceso externo, necesita también un contacto Acceso de suscriptor y especificar números DID (llamada directa a la extensión).



Para comprobar que se han creado los objetos de contacto, abra Usuarios y equipos de Active Directory y seleccione la unidad organizativa en la que se crearon los objetos. Los objetos de contacto deben aparecer en el panel de detalles.

