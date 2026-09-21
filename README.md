function dailyLog178() {
  const tasks = [
    { name: "Fix bugs", completed: 4, minutes: 40 },
    { name: "Write tests", completed: 6, minutes: 50 },
    { name: "Review code", completed: 3, minutes: 20 },
    { name: "Update docs", completed: 5, minutes: 30 }
  ];

  const totalCompleted = tasks.reduce(
    (sum, task) => sum + task.completed,
    0
  );

  const totalMinutes = tasks.reduce(
    (sum, task) => sum + task.minutes,
    0
  );

  const mostEfficient = tasks.reduce((best, task) =>
    task.completed / task.minutes > best.completed / best.minutes
      ? task
      : best
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalCompleted,
    totalTime: `${totalMinutes} minutes`,
    mostEfficientTask: mostEfficient.name,
    tasksPerHour: (
      (mostEfficient.completed / mostEfficient.minutes) * 60
    ).toFixed(1)
  };

  console.log("Daily Efficiency Report:", report);
}

dailyLog178();
