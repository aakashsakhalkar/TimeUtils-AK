# TimeUtils-AK ⏱️

A simple and handy Android time utility library to work with dates, time calculations, and formatting.

## 🔧 Installation

1. Add **JitPack** to your root `settings.gradle`:

```groovy
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven { url 'https://www.jitpack.io' }
    }
}
```

2. Add the dependency to your module-level `build.gradle`:

```groovy
dependencies {
    implementation 'com.github.aakashsakhalkar:TimeUtils-AK:v1.0'
}
```

## 🚀 Usage

Import the utility:

```java
import com.aakash.timeutils_ak.TimeUtils;
```

Then use any of its static methods. Here’s a complete example:

```java
try {
    Date oneMinuteAgo = new Date(System.currentTimeMillis() - 60000);
    String timeAgo = TimeUtils.timeAgo(oneMinuteAgo);

    Date oneDayAgo = new Date(System.currentTimeMillis() - 86400000);
    boolean isYesterday = TimeUtils.isYesterday(oneDayAgo);

    Date today = new Date();
    String dayName = TimeUtils.getDayName(today);
    String formattedDate = TimeUtils.formatDate(today, "dd MMM yyyy hh:mm:ss");
    String monthName = TimeUtils.getMonthName(today);

    Date birthDate = new SimpleDateFormat("yyyy-MM-dd").parse("1999-01-01");
    int age = TimeUtils.getAge(birthDate);

    int[] AgeBreakdown = TimeUtils.getAgeBreakdown(birthDate);

    Date start = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss").parse("2023-01-01 08:00:00");
    Date end = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss").parse("2023-01-03 10:30:00");
    String timeDiff = TimeUtils.getTimeDiff(start, end);

    boolean todayCheck = TimeUtils.isToday(new Date());

    Calendar tomorrowCal = Calendar.getInstance();
    tomorrowCal.add(Calendar.DAY_OF_YEAR, 1);
    boolean isTomorrow = TimeUtils.isTomorrow(tomorrowCal.getTime());

    boolean sameDayCheck = TimeUtils.isSameDay(new Date(), new Date());

    Calendar thisWeekDate = Calendar.getInstance();
    thisWeekDate.set(Calendar.DAY_OF_WEEK, Calendar.MONDAY);
    boolean thisWeek = TimeUtils.isThisWeek(thisWeekDate.getTime());

    int weekOfYear = TimeUtils.getWeekOfYear(today);
    Date threeDaysLater = TimeUtils.addDays(today, 3);

    Date startOfDay = TimeUtils.getStartOfDay(today);
    Date endOfDay = TimeUtils.getEndOfDay(today);

} catch (Exception e) {
    e.printStackTrace();
}
```

## 📦 Features

- `timeAgo(Date)` — "just now", "2 hrs ago", etc.
- `isToday(Date)`, `isYesterday(Date)`, `isTomorrow(Date)`
- `getDayName(Date)` — like "Monday"
- `getMonthName(Date)` — like "January"
- `formatDate(Date, pattern)` — returns formatted string
- `getAge(Date)` — age in years
- `getAgeBreakdown(Date)` — age in [years, months, days]
- `getTimeDiff(Date start, Date end)` — difference in `xd yh zm`
- `isSameDay(Date a, Date b)`
- `isThisWeek(Date)`
- `getWeekOfYear(Date)`
- `addDays(Date, int)`
- `getStartOfDay(Date)`
- `getEndOfDay(Date)`

## 📌 License

MIT – free to use, improve, and share.
