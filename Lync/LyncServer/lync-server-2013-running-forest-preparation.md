---
title: 'Lync Server 2013: ejecución de la preparación del bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4ed33466e9b31fbabb3432927baea8f087ea1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511127"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>Ejecutar la preparación del bosque para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Puede usar los cmdlets del shell de administración de Lync Server o de instalación para preparar el bosque. El cmdlet que prepara el bosque es **Enable-CsAdForest**.

Después de preparar el bosque, debe comprobar que la configuración global se haya replicado antes de llevar a cabo la preparación del dominio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Para preparar el bosque durante la instalación

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo de administradores de la empresa para el dominio raíz del bosque.

2.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación.

3.  Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

4.  En **Paso 3: Preparar bosque actual**, haga clic en **Ejecutar**.

5.  En la página **Preparar el bosque**, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > La preparación del bosque le permite elegir dónde desea situar los grupos universales para Lync Server 2013. Elija una ubicación que respete los requisitos de su organización.

    
    </div>

6.  En la página **Ejecución de comandos**, busque **Estado de la tarea: completado** y, a continuación, haga clic en **Ver registro**.

7.  En la columna **acción** , expanda **preparación del bosque**, busque un **\<Success\>** resultado de ejecución al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

8.  Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento **Sitios y servicios de Active Directory** del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio en todos los sitios de Active Directory para que la replicación en los sitios se produzca en cuestión de minutos.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Para usar cmdlets en la preparación del bosque

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo Admins. del dominio en el dominio raíz del bosque.

2.  Instale los componentes principales de Lync Server de la siguiente manera:
    
    1.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute Setup.exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el Paquete redistribuible de Microsoft Visual C++, haga clic en **Sí**.
    
    3.  El cuadro de diálogo del programa de instalación de Lync Server 2013 le pedirá que indique una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o haga clic en **Examinar** para buscar la ubicación que prefiera y, a continuación, en **Instalar**.
    
    4.  En la página Contrato de licencia, active **Acepto los términos del contrato de licencia** y haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

4.  Realizar
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Por ejemplo:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local. Si se crearon grupos universales previamente en un dominio que no es el dominio predeterminado, debe especificar el parámetro GroupDomain explícitamente.

5.  Espere a que se complete la replicación de Active Directory o fuércela en todos los controladores de dominio que se enumeran en el complemento **Sitios y servicios de Active Directory ** del controlador del dominio raíz del bosque antes de ejecutar la preparación del dominio.

6.  Compruebe que la preparación del bosque se ha realizado correctamente. Ejecute:
    
        Get-CsAdForest 
    
    Este cmdlet devuelve un valor de **LC \_ FORESTSETTINGS \_ estado \_ listo** si la preparación del bosque se ha realizado correctamente.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Uso de cmdlets para invertir la preparación del bosque para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Preparar el bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

