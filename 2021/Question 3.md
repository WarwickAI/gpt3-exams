# Question 3 (10/20)

## QUESTION 3a
You are helping to code a leader-board for a local Hack-a-thon. Users complete tasks, earn a score and their cumulative score from each task determines their position on the leaderboard. If they do particularly poorly, they can earn a negative score in some tasks, and so a User can have a negative score overall. A User is defined by a name, unique ID number and a score. The ID number is 8 characters long, and can contain both letters and numbers. Users can enter anonymously, in which case they will be given the same name as their ID number. When a User enters the competition, they start with a score of 0. Names and ID numbers cannot change.

Design an appropriate User class that stores the needed attributes, and has appropriate constructors?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
}
```

(3/3) - Very impressive, nice use of overloading, writes unnecessary code though

## QUESTION 3b
Write appropriate accessor and mutator methods for your class from 3a?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
}
```

(2/2) - Already did it, only score is allowed to change

## QUESTION 3c
3c Add the ability to increase and decrease the User’s score from 3b?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
    public void increaseScore(int amount) {
        this.score += amount;
    }
    public void decreaseScore(int amount) {
        this.score -= amount;
    }
}
```

(2/2) - Bad method but it works

## QUESTION 3d
3d A User can reattempt tasks, but can only receive a score for their initial completion of any task. Assuming each task has a unique ID between 0 (inclusive) and n (exclusive) where n is the number of tasks, update your class to ensure a User only receives a score for a task once. You may assume the existence of a static, final, variable numberOfTasks, which is set to n?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
    public void increaseScore(int amount) {
        this.score += amount;
    }
    public void decreaseScore(int amount) {
        this.score -= amount;
    }
    public void reattemptTask(int taskId) {
        if (taskId < 0 || taskId >= numberOfTasks) {
            throw new IllegalArgumentException();
        }
        if (taskIds.contains(taskId)) {
            throw new IllegalArgumentException();
        }
        taskIds.add(taskId);
    }
    private List<Integer> taskIds = new ArrayList<Integer>();
    private static final int numberOfTasks = 10;
}
```

(1/5) - Partial solution, correctly checks and maintains list of attempted tasks but never calls it

## QUESTION 3e
3e Users can join together into teams. Each team has a unique ID, name and score. A User can only be a member of a single team. Update your class to include the team a User is in. Assume the Team class already exists?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    private Team team;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
    public void increaseScore(int amount) {
        this.score += amount;
    }
    public void decreaseScore(int amount) {
        this.score -= amount;
    }
    public void reattemptTask(int taskId) {
        if (taskId < 0 || taskId >= numberOfTasks) {
            throw new IllegalArgumentException();
        }
        if (taskIds.contains(taskId)) {
            throw new IllegalArgumentException();
        }
        taskIds.add(taskId);
    }
    private List<Integer> taskIds = new ArrayList<Integer>();
    private static final int numberOfTasks = 10;
	
    private Team team;
    public void setTeam(Team team) {
        this.team = team;
    }
    public Team getTeam() {
        return team;
    }
}
```

(1/2) - Defined team twice but did get and set

## QUESTION 3f
If a user is in a team, their score is actually the sum of the team’s best score for each task. 
For example: Users 1, 2 and 3 are in a team. For 5 tasks: User 1 scored 0, 4, 7, 2 and -3. User 2 scored 3, 2, 9, 1 and 0. User 3 scored -1, 1, 1, 4 and 2. 
The total score for each user is 3 + 4 + 9 + 4 + 2 = 22, as we take the best score from the team for each task and sum them together. 
Assuming the Team object has a getMembers() method that returns an array of User objects representing the team members, write a method that calculates the score of a User. You may need to write additional methods, or add new attributes to your User class?

### ANSWER
```Java
public class User {
    private String name;
    private String id;
    private int score;
    private Team team;
    public User(String name, String id) {
        this.name = name;
        this.id = id;
        this.score = 0;
    }
    public User(String id) {
        this.name = id;
        this.id = id;
        this.score = 0;
    }
    public String getName() {
        return name;
    }
    public String getId() {
        return id;
    }
    public int getScore() {
        return score;
    }
    public void setScore(int score) {
        this.score = score;
    }
    public void increaseScore(int amount) {
        this.score += amount;
    }
    public void decreaseScore(int amount) {
        this.score -= amount;
    }
    public void reattemptTask(int taskId) {
        if (taskId < 0 || taskId >= numberOfTasks) {
            throw new IllegalArgumentException();
        }
        if (taskIds.contains(taskId)) {
            throw new IllegalArgumentException();
        }
        taskIds.add(taskId);
    }
    private List<Integer> taskIds = new ArrayList<Integer>();
    private static final int numberOfTasks = 10;
    private Team team;
    public void setTeam(Team team) {
        this.team = team;
    }
    public Team getTeam() {
        return team;
    }
    public double getScore() {
        double score = 0;
        for (Integer taskId: team.getMembers().get(0).getTaskIds()) {
            int bestScore = Integer.MIN_VALUE;
            for (User user: team.getMembers()) {
                if (user.getScore(taskId) > bestScore) {
                    bestScore = user.getScore(taskId);
                }
            }
            score += bestScore;
        }
        return score;
    }
}
```

(1/6) - Close, but uses wrong methods
