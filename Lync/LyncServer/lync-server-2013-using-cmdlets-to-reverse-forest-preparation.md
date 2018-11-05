---
title: 'Lync Server 2013: Usar cmdlets para invertir la preparación del bosque'
TOCTitle: Usar cmdlets para invertir la preparación del bosque
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48277190
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar cmdlets para invertir la preparación del bosque para Lync Server 2013

 

_**Última modificación del tema:** 2013-06-19_

Use el cmdlet **Disable-CsAdForest** para invertir el paso de preparación del bosque.

> [!CAUTION]  
> Si ejecuta el cmdlet <strong>Disable-CsAdForest</strong> en un entorno el que también se haya implementado una versión anterior de Lync Server, también se eliminará la configuración global de la versión anterior.



## Para usar los cmdlets para invertir la preparación del bosque

1.  Inicie sesión en un equipo que se haya unido a un dominio como miembro del grupo Admins. del dominio en el dominio raíz del bosque.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Por ejemplo:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    El parámetro Force especifica si se debe forzar la ejecución de la tarea. Si este parámetro no está presente, el comando no se ejecutará aunque un dominio del bosque esté preparado para Lync Server 2013. Si se especifica el parámetro Force, la acción continuará sea cual sea el estado de otros dominios del bosque.
    
    Si no especifica el parámetro GroupDomain, el valor predeterminado es el dominio local.

## Vea también

#### Tareas

[Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md)  

#### Otros recursos

[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)

