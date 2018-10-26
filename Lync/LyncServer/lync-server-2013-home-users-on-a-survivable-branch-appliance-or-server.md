---
title: "Usuarios particulares en una aplicación o un servidor de sucursal con supervivencia"
TOCTitle: Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48277267
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013

 

_**Última modificación del tema:** 2014-12-10_

El proceso de hospedar usuarios en una Aplicación de sucursal con funciones de supervivencia o un Servidor de sucursal con funciones de supervivencia es similar al de hospedarlos en un Grupo de servidores front-end. Efectúe el procedimiento de la Aplicación de sucursal con funciones de supervivencia o el Servidor de sucursal con funciones de supervivencia en el sitio central.

## Para hospedar a usuarios en un servidor o una aplicación de sucursal con funciones de supervivencia

1.  Antes de trasladar usuarios al Servidor de sucursal con funciones de supervivencia, abra el Shell de administración de Lync Server y siga el procedimiento que se indica a continuación:
    
      - Ejecute el cmdlet **Test-CsPstnOutboundCall** para comprobar que Servidor de sucursal con funciones de supervivencia se esté ejecutando y que se haya configurado la conectividad con RTC. Si debe modificar las propiedades de las puertas de enlace de RTC, use el cmdlet **Set-CsPstnGateway**.
    
      - Ejecute el cmdlet **Get-CsVoicePolicy** para comprobar que los usuarios que van a hospedarse en el Servidor de sucursal con funciones de supervivencia tengan la correspondiente directiva de enrutamiento VoIP. Si debe modificar la directiva de VoIP, use el cmdlet **Set-CsVoicePolicy**.
    
      - Ejecute el cmdlet **Get-CsVoicemailReroutingConfiguration** para comprobar que se haya definido la configuración del cambio de ruta del correo de voz. Si debe modificar la configuración del cambio de ruta del correo de voz, use el cmdlet **Set-CsVoicemailReroutingConfiguration**.

2.  En el Shell de administración de Lync Server, ejecute el cmdlet **Move-CsUser** para hospedar a usuarios.


> [!NOTE]
> Use también Panel de control de Lync Server para comprobar los requisitos previos y hospedar a usuarios.



## Vea también

#### Otros recursos

[Test-CsPstnOutboundCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)

