---
title: "Lync Server 2013 : Conf. du chiff. multimédia pour les fournisseurs publics"
TOCTitle: Configurar el cifrado de medios para proveedores públicos
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48276304
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el cifrado de medios para proveedores públicos en Lync Server 2013

 

_**Última modificación del tema:** 2014-12-12_

Para más información sobre los requisitos de licencia y sobre cómo completar el proceso de aprovisionamiento, consulte la guía de aprovisionamiento para la conectividad de mensajería instantánea pública en Microsoft Lync Server, Office Communications Server y Live Communications Server en [http://go.microsoft.com/fwlink/p/?linkId=155970](http://go.microsoft.com/fwlink/p/?linkid=155970)

Si va a implementar una federación de audio y vídeo (A/V) con Windows Live Messenger, debe modificar dos parámetros: el nivel de cifrado de Lync Server y la directiva EnablePublicCloudAccess. De forma predeterminada, el nivel de cifrado está configurado en Requerido. Debe cambiar esta opción a Compatible. Si la directiva EnablePublicCloudAccess está definida en falso, debe definirse en **Verdadero** . Puede hacerlo desde el Shell de administración de Lync Server.

> [!IMPORTANT]  
> Más que nunca, Lync es una potente herramienta para la conexión entre organizaciones e individuos de todo el mundo. Aparte de la licencia de acceso de cliente (CAL) estándar de Lync, la federación con Windows Live Messenger no exige ninguna otra licencia de usuario o dispositivo adicional. El próximo año, la federación con Skype se agregará a esta lista, lo que les permitirá a los usuarios de Lync llegar a cientos de millones de personas con mensajería instantánea y telefonía.



## Configurar la federación para Windows Live

1.  Inicie el Shell de administración de Lync Server en el servidor front-end: haga clic en **Inicio** , **Todos los programas** , **Microsoft Lync Server 2013** y **Shell de administración de Lync Server**.

2.  Desde el símbolo del sistema, escriba los siguientes comandos:
    
    ```
    Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
    ```
    ```
    Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```

    > [!NOTE]
    > Este es un paso necesario porque Windows Live Messenger no admite el cifrado de audio/vídeo. El comando configura su directiva global en una configuración de cifrado compatible en lugar de requerir el cifrado de los datos de audio y vídeo. Los clientes que admiten el cifrado continúan usando el cifrado, como Lync 2013.


