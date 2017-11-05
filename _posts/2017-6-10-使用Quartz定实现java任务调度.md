---
bg: "tools.jpg"
layout: post
title:  "使用Quartz定实现java任务调度"
crawlertitle: "使用Quartz定实现java任务调度"
summary: "使用Quartz定实现java任务调度"
date:   2017-5-1 12:55:29 +0800
categories: posts
tags: ['java']
author: haohhxx
---

直接在Quartz官网上找到的例子。使用的时候继承Quartz的Job类，实现其execute方法。
JobDataMap用于传递任务执行所需的参数。

```xml
<!-- quartz 的jar -->
<dependency>
    <groupId>org.quartz-scheduler</groupId>
    <artifactId>quartz</artifactId>
    <version>2.2.1</version>
</dependency>
<dependency>
    <groupId>org.quartz-scheduler</groupId>
    <artifactId>quartz-jobs</artifactId>
    <version>2.2.1</version>
</dependency>
```

```java
import org.haohhxx.hotevent.HotEventTask.taskentity.Product;
import org.quartz.*;

import static org.quartz.CronScheduleBuilder.cronSchedule;
import static org.quartz.JobBuilder.newJob;
import static org.quartz.TriggerBuilder.newTrigger;

/**
 * Created by Administrator on 2017/7/18.
 * 在线cron表达式生成工具 http://cron.qqe2.com/
 */
public class QuartzScheduling {

    public void executeTask(Product product, Class<? extends Job> executeJob)throws SchedulerException {

        SchedulerFactory schedFact = new org.quartz.impl.StdSchedulerFactory();
        Scheduler sched = schedFact.getScheduler();
        sched.start();

        JobDataMap jobmess = new JobDataMap();
        jobmess.put("product",product);
        JobDetail job = newJob(executeJob)
                .withIdentity("Job:"+product.getEventId(), "group_"+product.getEventId())
                .setJobData(jobmess)
                .build();

        // Trigger the src.job to run now, and then every 40 seconds
        Trigger trigger = newTrigger()
                .withIdentity("Trigger:"+product.getEventId(), "group_"+product.getEventId())
                .startNow()
                .withSchedule(cronSchedule(product.getCronTime()))
                .build();

        // Tell quartz to schedule the src.job using our trigger
        sched.scheduleJob(job, trigger);
    }

}

```
