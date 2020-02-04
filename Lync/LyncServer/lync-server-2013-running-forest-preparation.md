---
title: 'Lync Server 2013: Ejecutar la preparación del bosque'
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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Ejecutar la preparación del bosque para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Puede usar el programa de instalación o los cmdlets del shell de administración de Lync Server para preparar el bosque. El cmdlet que prepara el bosque es **enable-CsAdForest**.

Después de preparar el bosque, debe comprobar que la configuración global se ha replicado antes de ejecutar la preparación del dominio.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>Para usar el programa de instalación para preparar el bosque

1.  Inicie sesión en un equipo unido a un dominio como miembro del grupo administradores de empresa del dominio raíz del bosque.

2.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación.

3.  Haga clic en **Preparar Active Directory** y espere hasta que se determine el estado de implementación.

4.  En el **paso 3: preparar el bosque actual**, haga clic en **Ejecutar**.

5.  En la página **preparar el bosque** , haga clic en **siguiente**.
    
    <div>
    

    > [!NOTE]  
    > La preparación del bosque le permite elegir dónde ubicar los grupos universales para Lync Server 2013. Elija una ubicación que respete los requisitos de su organización.

    
    </div>

6.  En la página **Ejecución de comandos**, busque **Estado de tarea: Completado** y haga clic en **Ver registro**.

7.  En la columna **acción** , expanda **preparar el bosque**, busque un ** \<\> ** resultado de ejecución correcta al final de cada tarea para comprobar que la preparación del bosque se completó correctamente, cierre el registro y, a continuación, haga clic en **Finalizar**.

8.  Espere a que se complete la replicación de Active Directory, o fuerce la replicación en todos los controladores de dominio que aparecen en el complemento **sitios y servicios de Active** Directory para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio. Fuerce la replicación entre los controladores de dominio de todos los sitios de Active Directory para que la replicación dentro de los sitios se produzca en minutos.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Para usar cmdlets para preparar el bosque

1.  Inicie sesión en un equipo unido a un dominio como miembro del grupo administradores del dominio en el dominio raíz del bosque.

2.  Instale los componentes básicos de Lync Server de la siguiente manera:
    
    1.  Desde la carpeta o los medios de instalación de Lync Server 2013, ejecute setup. exe para iniciar el Asistente para la implementación de Lync Server.
    
    2.  Si se le pide que instale el redistribuible de Microsoft Visual C++, haga clic en **sí**.
    
    3.  En el cuadro de diálogo instalación de Lync Server 2013 se le pide una ubicación para instalar los archivos de Lync Server. Elija la ubicación predeterminada o **Desplácese** hasta la ubicación que desee y, a continuación, haga clic en **instalar**.
    
    4.  En la página contrato de licencia, seleccione **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar**. El instalador instala los componentes principales de Lync Server 2013.

3.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

4.  Ejecute:
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    Por ejemplo:
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local. Si se han creado grupos universales en un dominio que no es el dominio predeterminado, debe especificar el parámetro GroupDomain de forma explícita.

5.  Espere a que se complete la replicación de Active Directory, o fuerce la replicación en todos los controladores de dominio que aparecen en el complemento **sitios y servicios de Active** Directory para el controlador de dominio raíz del bosque, antes de ejecutar la preparación del dominio.

6.  Verifique que la preparación del bosque se haya realizado correctamente. Ejecute:
    
        Get-CsAdForest 
    
    Este cmdlet devuelve un valor de **LC\_FORESTSETTINGS\_estado\_listo** si la preparación del bosque se realizó correctamente.

</div>

<div>

## <a name="see-also"></a>Vea también


[Usar cmdlets para invertir la preparación del bosque para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

