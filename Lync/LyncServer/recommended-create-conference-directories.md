---
title: (Recomendado) Crear directorios de conferencia
TOCTitle: (Recomendado) Crear directorios de conferencia
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63232644
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Recomendado) Crear directorios de conferencia

 

_**Última modificación del tema:** 2014-10-03_

Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia mediante Lync 2013 y el identificador de conferencia numérico que un participante de una conferencia de acceso telefónico local usa para unirse a la conferencia. El formato del identificador de conferencia es el siguiente:

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo. Si aplica esta sugerencia, los Id. de conferencia, por lo general, se mantendrán cortos. Sin embargo, cuando el número de directorios de conferencia (en los grupos) exceda de 9, la longitud del id. de conferencia aumentará para dar soporte a otras conferencias.

## Creación de un directorio de conferencias

1.  En Shell de administración de Lync Server, escriba el siguiente cmdlet:
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    Por ejemplo, el siguiente crea un directorio de conferencia con la identidad 42, hospedado en el grupo atl-cs-001.litwareinc.com:
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

## Vea también

#### Conceptos

[Planeación de las conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  

#### Otros recursos

[New-CsConferenceDirectory](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsConferenceDirectory)

