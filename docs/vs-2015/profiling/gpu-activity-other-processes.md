---
title: Активность GPU (другие процессы) | Документы Майкрософт
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.gpuother
- vs.cv.threads.timeline.gpuactivity
ms.assetid: 8a68df65-eb63-452f-9285-fb4ffc92f2b2
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5b38423bd629dee0f518e0f62eedcf7c55c1db0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789841"
---
# <a name="gpu-activity-other-processes"></a>Активность GPU (другие процессы)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Сегменты **Активность GPU (другие процессы)** в представлении потоков визуализатора параллелизма представляют моменты времени, когда GPU выполнял обработку запросов от имени других процессов в системе. Эти запросы отправляются в GPU как пакеты прямого доступа к памяти (DMA).  Длина сегмента представляет количество времени, затраченного на обработку пакета графическим процессором.  
  
 При выборе такого типа сегмента в отчете на вкладке **Текущие** отображаются сведения об обработанном пакете.  Эти сведения включают время ожидания пакета в очереди оборудования, связанной с ядром DirectX; процесс, отправивший пакет; и время, которое потребовалось для обработки пакета.



