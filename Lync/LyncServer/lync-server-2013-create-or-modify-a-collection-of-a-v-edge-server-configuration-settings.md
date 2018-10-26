---
title: "Crear/modificar conjuntos de opciones de configación del servidor perimetral A/V"
TOCTitle: "Créa. ou mod. d’une collection de param. de configuration de serveur Edge A/V"
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49889063
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de conjuntos de opciones de configuración del servidor perimetral A/V

 

_**Última modificación del tema:** 2012-11-01_

El servicio perimetral A/V proporciona una manera para que los usuarios internos (usuarios que están conectados a la red organizativa) compartan audio y vídeo con usuarios externos (usuarios que no están conectados a la red organizativa). El servicio perimetral A/V se administra principalmente mediante los valores de configuración del servicio perimetral A/V, que pueden configurarse en el ámbito del sitio o en el ámbito del servicio (es decir, se pueden configurar para un servidor perimetral A/V individual).

Al instalar Lync Server, se crea una colección global de valores de configuración del servicio perimetral A/V para usted. Además, puede usar el Shell de administración de Lync Server y el cmdlet de New-CsAVEdgeConfiguration para crear unos nuevos valores en el ámbito del sitio o el ámbito del servicio (es decir, para un servidor perimetral A/V individual). Si crea nuevos valores, tenga en cuenta que:

  - Los valores configurados en el ámbito del servicio (es decir, en un servidor individual) tienen prioridad sobre todo.

  - Los valores configurados en el ámbito del sitio tienen prioridad sobre los valores configurados en el ámbito global. Sin embargo, los valores del ámbito del servicio también cambiarán los valores del ámbito del sitio.

  - Se usarán los valores del ámbito global solo si no hay valores del servicio configurados en el servidor individual y si no hay ninguna valores del sitio para el sitio donde se encuentra el servidor.

Los valores pueden modificarse después con el cmdlet Set-CsAVEdgeConfiguration. Para más información, vea los temas de ayuda de los cmdlets de [New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration) y [Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration).

## Creación de nuevos valores de configuración de servicio perimetral A/V en el ámbito del sitio

  - El comando siguiente crea una nueva colección de valores de configuración del servicio perimetral A/V para el sitio Redmond.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

## Creación de valores de configuración personalizados del servicio perimetral A/V en el ámbito del sitio

  - Ya que no se incluyeron parámetros adicionales, estos nuevos valores usarán los valores predeterminados para el servicio perimetral A/V. Como alternativa, puede agregar parámetros adicionales y valores de parámetros para crear una colección personalizada. Por ejemplo, este comando establece la propiedad MaxTokenLifetime en 4 horas (04 horas : 00 minutos : 00 segundos):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

## Creación de valores de configuración personalizados del servicio perimetral A/V en el ámbito del servicio

  - Este comando crea una colección similar aplicada al servidor perimetral A/V atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

## Modificación de valores de configuración existente del servicio perimetral A/V

  - En este ejemplo, se usa el cmdlet de Set-CsAVEdgeConfiguration para cambiar la vigencia máxima del token en el sitio Redmond a 12 horas:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

## Vea también

#### Tareas

[Devolución de información de configuración del servidor perimetral de A/V](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Eliminación de un conjunto existente de opciones de configuración del servidor perimetral A/V](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Otros recursos

[Servidores perimetrales de audio y vídeo (A/V) en Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration)  
[Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration)

