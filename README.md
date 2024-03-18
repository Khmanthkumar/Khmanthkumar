
public class Organization implements Cloneable {
    private int organizationCode;
    private String organizationName;
    private String organizationAddress;

    // Constructor
    public Organization(int code, String name, String address) {
        this.organizationCode = code;
        this.organizationName = name;
        this.organizationAddress = address;
    }

    // Getters and Setters
    public int getOrganizationCode() {
        return organizationCode;
    }

    public void setOrganizationCode(int organizationCode) {
        this.organizationCode = organizationCode;
    }

    public String getOrganizationName() {
        return organizationName;
    }

    public void setOrganizationName(String organizationName) {
        this.organizationName = organizationName;
    }

    public String getOrganizationAddress() {
        return organizationAddress;
    }

    public void setOrganizationAddress(String organizationAddress) {
        this.organizationAddress = organizationAddress;
    }

    // Method to print object details
    public void printDetails() {
        System.out.println("Organization Code: " + organizationCode);
        System.out.println("Organization Name: " + organizationName);
        System.out.println("Organization Address: " + organizationAddress);
    }

    // Override clone method
    @Override
    public Organization clone() {
        try {
            return (Organization) super.clone();
        } catch (CloneNotSupportedException e) {
            // This should never happen since Organization implements Cloneable
            throw new InternalError(e);
        }
    }

    public static void main(String[] args) {
        Organization org1 = new Organization(1, "Org1", "Address1");

        // Creating a clone of org1
        Organization org2 = org1.clone();

        // Printing details of org1 and its clone org2
        System.out.println("Details of org1:");
        org1.printDetails();
        System.out.println();

        System.out.println("Details of org2 (clone of org1):");
        org2.printDetails();
    }
}
