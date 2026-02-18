using CarService.Data;
namespace CarService.Services;

public interface INotificationService { Task SendAsync(string msg); } // Интерфейс 1
public interface ICarRepository { Task AddAsync(Car car); } // Интерфейс 2

public class CarBusinessService {
    private readonly ICarRepository _repo;
    private readonly INotificationService _notification;

    public CarBusinessService(ICarRepository repo, INotificationService notification) {
        _repo = repo;
        _notification = notification;
    }

    public async Task RegisterCarAsync(Car car) {
        await _repo.AddAsync(car);
        await _notification.SendAsync("Колата е добавена успешно!");
    }
}
