---
title: "Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition"
TOCTitle: "Conf. de la qual. de service sur les appareils Microsoft Lync Phone Edition"
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48276203
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la calidad de servicio en dispositivos Microsoft Lync Phone Edition

 

_**Última modificación del tema:** 2012-11-01_

Aunque la función Calidad del servicio (QoS) no se habilita de manera predeterminada para dispositivos como los iPhones, sí se habilita de manera predeterminada para dispositivos que funcionen con Lync Phone Edition. (Dichos dispositivos suelen conocerse como teléfonos de comunicaciones unificadas o teléfonos UC.) Para comprobarlo, ejecute el siguiente comando de Windows PowerShell desde dentro del Shell de administración de Lync Server:

    Get-CsUCPhoneConfiguration

Si no ha hecho ningún cambio en la configuración de su teléfono UC, obtendrá como respuesta una información que presentará el siguiente aspecto:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Para fines de Calidad del servicio, solo es de interés una de estas propiedades: VoiceDiffServTag. VoiceDiffServTag representa el valor DSCP asignado al tráfico de voz proveniente de un dispositivo Lync Phone Edition.


> [!NOTE]
> El parámetro Voice8021p ya no se admite en Lync Server 2013. El parámetro sigue siendo válido para compatibilidad con versiones anteriores (Microsoft Lync Server 2010); ahora bien, no tiene efecto alguno en dispositivos que se usen con Lync Server 2013.



En la mayoría de redes no debe suponer ningún problema marcar los paquetes de Lync Phone Edition con un valor VoiceDiffServTag de 40. Ahora bien, 40 no es el valor que suele utilizarse para tráfico de audio, que casi siempre se marca con el código 46 de DSCP. Con el fin de mantener la coherencia en toda la red, es posible que le interese cambiar la propiedad VoiceDiffServTag de sus teléfonos UC a 46.

Para ello, puede usar o bien Windows PowerShell o el Panel de control de Lync Server. Para modificar el valor de VoiceDiffServTag con Windows PowerShell, ejecute el siguiente comando desde dentro del Shell de administración de Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

El comando anterior modifica la recopilación global de opciones de configuración de teléfono UC. Ahora bien, tenga en cuenta que la configuración de teléfono UC también puede asignarse al ámbito del sitio. Para modificar la configuración de teléfono UC en el ámbito del sitio, deberá especificar la identidad del sitio. Por ejemplo:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

También puede utilizar el siguiente comando para modificar simultáneamente todos sus parámetros de configuración de teléfono UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Si prefiere hacer este cambio utilizando el Panel de control de Lync Server, inicie el Panel de control y luego lleve a cabo el siguiente procedimiento:

1.  Haga clic en **Clientes** y, a continuación, en **Configuración de dispositivo**.

2.  En la pestaña **Configuración de dispositivo**, haga doble clic en la colección de parámetros de configuración que desee modificar (por ejemplo, **Global**).

3.  En el cuadro de diálogo **Editar configuración de dispositivo**, establezca en el cuadro **Calidad de voz del servicio (QoS)** el valor **46** y luego haga clic en **Confirmar**.

Si tiene varias recopilaciones de opciones de configuración de teléfono UC, deberá repetir este proceso para cada una de ellas. Panel de control de Lync Server no permite modificar varias recopilaciones de opciones de configuración a un mismo tiempo.

Si en su organización tiene dispositivos que no se basan en el sistema operativo Windows (por ejemplo, iPhones), dichos dispositivos no se verán afectados por los cambios en la opción de configuración VoiceDiffServTag. Si desea modificar los valores de DSCP de dichos dispositivos, deberá consultar con el manual de administración de cada tipo de dispositivo.

