import java.io.*;
import java.util.ArrayList;
import java.util.List;

public class Filehandler {

    public static void saveEmployers(String filename, List<Employer> employers) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            for (Employer emp : employers) {
                writer.write( emp.getEmail() + "," + emp.password);
                writer.newLine();
            }
        } catch (IOException e) {
            System.out.println("Error saving employers: " + e.getMessage());
        }
    }

    public static void saveJobSeekers(String filename, List<Jobseeker> seekers) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            for (Jobseeker seeker : seekers) {
                writer.write(seeker.getEmail() + "," + seeker.getResume() + "," + seeker.password);
                writer.newLine();
            }
        } catch (IOException e) {
            System.out.println("Error saving job seekers: " + e.getMessage());
        }
    }

    public static void saveJobs(String filename, List<Job> jobs) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            for (Job job : jobs) {
                writer.write(job.getJobId() + "," + job.getTitle() + "," + job.getDescription() + "," + job.getSalary());
                writer.newLine();
            }
        } catch (IOException e) {
            System.out.println("Error saving jobs: " + e.getMessage());
        }
    }

    public static void saveApplications(String filename, List<Jobapplication> applications) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            for (Jobapplication app : applications) {
                writer.write( app.getJobId() + "," + app.getJobseekeremail());
                writer.newLine();
            }
        } catch (IOException e) {
            System.out.println("Error saving applications: " + e.getMessage());
        }
    }

    public static List<Employer> loadEmployers(String filename) {
        List<Employer> employers = new ArrayList<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] data = line.split(",");
                if (data.length == 2) {
                    Employer emp = new Employer(data[0], data[1]);
                    employers.add(emp);
                }
            }
        } catch (IOException e) {
            System.out.println("Error loading employers: " + e.getMessage());
        }
        return employers;
    }

    public static List<Jobseeker> loadJobSeekers(String filename) {
        List<Jobseeker> seekers = new ArrayList<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] data = line.split(",");
                if (data.length == 3) {
                    Jobseeker seeker = new Jobseeker(data[0], data[1], data[2]);
                    seekers.add(seeker);
                }
            }
        } catch (IOException e) {
            System.out.println("Error loading job seekers: " + e.getMessage());
        }
        return seekers;
    }

    public static List<Job> loadJobs(String filename) {
        List<Job> jobs = new ArrayList<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] data = line.split(",");
                if (data.length == 4) {
                    Job job = new Job(data[0], data[1], data[2], Double.parseDouble(data[3]));
                    jobs.add(job);
                }
            }
        } catch (IOException e) {
            System.out.println("Error loading jobs: " + e.getMessage());
        }
        return jobs;
    }

    public static List<Jobapplication> loadApplications(String filename) {
        List<Jobapplication> applications = new ArrayList<>();
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] data = line.split(",");
                if (data.length == 2) {
                    Jobapplication app = new Jobapplication(data[0], data[1]);
                    applications.add(app);
                }
            }
        } catch (IOException e) {
            System.out.println("Error loading applications: " + e.getMessage());
        }
        return applications;
    }
}
